---
title: Vim Config
date: 2025-03-20
published: true
---
# Vim Config
分享我的vim配置
<!-- more -->

```
set nobackup                            # 不自动创建备份文件
set noswapfile                          # 不自动创建交换文件
set nu                                  # 显示行号
set ai                                  # 自动缩进
set si                                  # 智能缩进
set scrolloff=5                         # 滚动时保留5行的边界
set softtabstop=4                       # 4个空格=1个tab
set shiftwidth=4                        # 每次缩进4个空格
set tabstop=4                           # tab的宽度为4
set expandtab                           # 空格代替tab
set wildmenu                            # 命令行自动补全
set clipboard=unnamedplus               # 使用系统剪切板
set relativenumber                      # 显示相对行号

set background=dark                     # 设置背景为深色
syntax enable                           # 语法高亮
filetype plugin indent on               # 文件类型检测

```


