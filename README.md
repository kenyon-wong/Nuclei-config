# Nuclei-config

Nuclei 自定义配置文件备份

> [!note]
> 使用配置文件时，可能存在一个bug：Windows和类unix系统间默认的目录分隔符不一致，可能导致到引入模板或者排除模板无效
> 建议使用本配置文件时，提前检查相关配置模板的目录分隔符是否符合系统要求

使用方式：

```bash
nuclei -config My-nuclei-config.yaml -l targets.txt
```



