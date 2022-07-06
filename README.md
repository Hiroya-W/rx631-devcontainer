## rx631-devcontainer

CPUボード RX631（R5F5631MDDFL）を利用した [HM-StarterKit 手のひらサイズのマイクロマウス学習キット](https://rt-net.jp/products/hm-starterkit/) の開発用 dev-container です。

## Requirements

ToolChain インストーラを用いて Dockerfile をビルドします。 
`gcc-8.3.0.202202-GNURX-ELF.run` を取得して、`.devcontainer/` に配置してください。

別のバージョンのToolChainを利用する場合は、 `.devcontainer/Dockerfile` の `RXINSTALLER` を適切に変更してください。

```Dockerfile
ARG RXINSTALLER="gcc-8.3.0.202202-GNURX-ELF.run"
```

## 参考

- [番外編 Part1 MacOSで環境構築を始めよう！ – しゅうのマイクロマウス研修](https://rt-net.jp/mobility/archives/13282)
- [hirakuni45/RX: Renesas RX Microcontroller, C++ framework, Library, Sample](https://github.com/hirakuni45/RX)
