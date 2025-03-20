---
title: Vim Config
date: 2025-03-20
published: true
---
> 分享我的vim配置 

<!-- more -->

##  基础配置
```
set nobackup                            " 不自动创建备份文件
set noswapfile                          " 不自动创建交换文件
set nu                                  " 显示行号
set ai                                  " 自动缩进
set si                                  " 智能缩进
set scrolloff=5                         " 滚动时保留5行的边界
set softtabstop=4                       " 4个空格=1个tab
set shiftwidth=4                        " 每次缩进4个空格
set tabstop=4                           " tab的宽度为4
set expandtab                           " 空格代替tab
set wildmenu                            " 命令行自动补全
set clipboard=unnamedplus               " 使用系统剪切板
set relativenumber                      " 显示相对行号

set background=dark                     " 设置背景为深色
syntax enable                           " 语法高亮
filetype plugin indent on               " 文件类型检测
```

## 按键映射
```
inoremap jk <ESC>            " 插入模式下 jk 退出插入模式
vnoremap jk <ESC>            " 视图模式下 jk 退出插入模式

nnoremap <silent> <Space>sv :vsplit<CR>   " 空格加sv  垂直分屏
nnoremap <silent> <Space>sh :split<CR>    " 空格加sh  水平分屏
nnoremap <C-h> <C-w>h                     " 移动到左边的窗口
nnoremap <C-j> <C-w>j                     " 移动到下面的窗口
nnoremap <C-k> <C-w>k                     " 移动到上面的窗口 
nnoremap <C-l> <C-w>l                     " 移动到右边的窗口

nnoremap <silent> <Space>sc :close<CR>    " 关闭当前窗口
nnoremap <silent> <Space>so :only<CR>     " 关闭其他窗口

```

## 自动命令
```
" 当文件类型为C时 <F5> 运行当前文件
autocmd filetype c nnoremap <F5> :!gcc % -o %< && ./%< <CR>
" 当文件类型为python时 <F5> 运行当前文件
autocmd FileType python nnoremap <F5> :w<CR>:!clear && python3 %<CR>
```

## 插件
> plug.vim   => 插件管理器   
> coc.nvim   => 智能补全  

## 插件快捷键
```
" coc.nvim  
" 在插入模式下，如果补全菜单可见，按 Tab 确认选择，否则正常插入制表符
inoremap <silent><expr> <TAB> coc#pum#visible() ? coc#pum#confirm(): "\<TAB>"

" 在普通模式下，按 K 显示光标下的词的信息（悬停提示）
nnoremap <silent> K :call CocAction('doHover')<CR>

" 在普通模式下，按 gd 跳转到光标下的词的定义位置
nnoremap <silent> gd :call CocAction('jumpDefinition')<CR>

" 在普通模式下，按 gr 跳转到光标下的词的所有引用位置
nnoremap <silent> gr :call CocAction('jumpReferences')<CR>

" 在普通模式下，按空格+rn 重命名光标下的词
nnoremap <silent> <Space>rn <Plug>(coc-rename)

" 在插入模式下，如果补全菜单可见，按 Ctrl+j 选择下一个补全项，否则正常插入 Ctrl+j
inoremap <silent><expr> <C-j> coc#pum#visible() ? coc#pum#next(1) : "\<C-j>"

" 在插入模式下，如果补全菜单可见，按 Ctrl+k 选择上一个补全项，否则正常插入 Ctrl+k
inoremap <silent><expr> <C-k> coc#pum#visible() ? coc#pum#prev(1) : "\<C-k>"

" 在插入模式下，如果补全菜单可见，按 Enter 确认选择，否则正常插入换行符
inoremap <silent><expr> <CR> coc#pum#visible() ? coc#pum#confirm() : "\<CR>"
" ------
```
>tips:  
>禁用cocc.nvim的内嵌类型提示和诊断
>:CocConfig  
>输入:  
>{  
>"inlayHint.enable": false   
>"diagnostic.enable": false
>}  



