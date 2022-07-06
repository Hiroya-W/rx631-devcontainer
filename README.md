## rx631-devcontainer

CPUボード RX631（R5F5631MDDFL）を利用した [HM-StarterKit 手のひらサイズのマイクロマウス学習キット](https://rt-net.jp/products/hm-starterkit/) の開発用 dev-container です。

CS+ではなく、GCC for Renesas ToolChainを用いています。

```bash
git clone https://github.com/Hiroya-W/rx631_gcc_projects.git --recursive
```

## Requirements

ToolChain インストーラを用いて Dockerfile をビルドします。 
`gcc-8.3.0.202202-GNURX-ELF.run` を取得して、`.devcontainer/` に配置してください。

ToolChainは以下から取得出来ますが、インストーラのダウンロードには、Renesasアカウントの登録が必要です。

- [GCC for Renesas X.X.X.YYYYMM-GNURX Toolchain](https://llvm-gcc-renesas.com/ja/rx-download-toolchains/)

別のバージョンのToolChainを利用する場合は、 `.devcontainer/Dockerfile` の `RXINSTALLER` を適切に変更してください。

```Dockerfile
ARG RXINSTALLER="gcc-8.3.0.202202-GNURX-ELF.run"
```

## Source Code

e2 studio で GCC for Renesas ToolChain 向けプロジェクトとして生成したソースコードと Makefile を配置しています。

C++向けコードは以下のリポジトリも参考にしてください。

[Hiroya-W/rx631_gcc_projects](https://github.com/Hiroya-W/rx631_gcc_projects)

## 参考

- [番外編 Part1 MacOSで環境構築を始めよう！ – しゅうのマイクロマウス研修](https://rt-net.jp/mobility/archives/13282)
- [hirakuni45/RX: Renesas RX Microcontroller, C++ framework, Library, Sample](https://github.com/hirakuni45/RX)
- [Hiroya-W/rx631_gcc_projects: Source code for RX631 using GCC for Renesas Toolchain](https://github.com/Hiroya-W/rx631_gcc_projects)
