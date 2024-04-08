# My Neovim Configuration Guide

## Introduction

Config neovim stuff.

## Table of Contents

- [Installation](#installation)
  - [Neovim](#neovim)
  - [Lazyvim](#lazyvim)
- [Configuration](#configuration)
  - [Basic Configuration](#basic-configuration)
  - [Options](#options)
    - [WSL Specific Configuration](#wsl-specific-configuration)
  - [Key Bindings](#key-bindings)
- [Plugins](#plugins)
  - [Installing Plugins](#installing-plugins)
  - [Recommended Plugins](#recommended-plugins)
- [Customization](#customization)
  - [Themes and Colors](#themes-and-colors)
  - [Status Line](#status-line)
- [Advanced Usage](#advanced-usage)
  - [Custom Functions](#custom-functions)
  - [Automation Scripts](#automation-scripts)
- [Troubleshooting](#troubleshooting)
  - [Common Issues](#common-issues)
  - [Performance Optimization](#performance-optimization)
- [Contributing](#contributing)
- [Credits](#credits)
- [License](#license)

## Installation

### Neovim

Instructions for installing Neovim from GitHub.

- Visit [Neovim's Installation Guide](https://github.com/neovim/neovim/blob/master/INSTALL.md) for detailed installation instructions.

### Lazyvim

How to download and install Lazyvim.

- Follow the installation guide at [Lazyvim Installation](https://www.lazyvim.org/installation).

## Configuration

### Basic Configuration

Overview of your basic Neovim setup, including initial settings and preferences.

### Options

Detailed explanation of configured options in your `init.vim` or `init.lua` files.

#### WSL Specific Configuration

Special configuration needed for running under WSL.

```lua
if vim.fn.has("wsl") == 1 then
  vim.g.clipboard = {
    name = "WslClipboard",
    copy = {
      ["+"] = "clip.exe",
      ["*"] = "clip.exe",
    },
    paste = {
      ["+"] = 'powershell.exe -c [Console]::Out.Write($(Get-Clipboard -Raw).tostring().replace("`r", ""))',
      ["*"] = 'powershell.exe -c [Console]::Out.Write($(Get-Clipboard -Raw).tostring().replace("`r", ""))',
    },
    cache_enabled = 0,
  }
end
