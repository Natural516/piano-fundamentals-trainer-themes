# Bocchi 1.1.0 实机截图

这些图片是正式应用的真实运行画面，不是设计预览或生成图。

- 采集日期：2026-10-02（Asia/Hong_Kong）。
- 应用：Piano Fundamentals Trainer Android 1.6.0，versionCode 14，正式包 `com.pianofundamentals.trainer`。
- 主题：`natural516.bocchi` / 孤独摇滚 1.1.0；截图前后均保持原本已启用的 1.1.0，没有重新导入或修改主题包。
- 设备：Lenovo TB375FC 横屏；原始及展示尺寸均为 **2944 × 1840**。
- MIDI：练习截图连接真实 Roland FP-30X，输入端口已打开；没有发送模拟 MIDI，也没有为了展示而完成题目。
- 来源：通过 Android `adb exec-out screencap -p` 获取完整屏幕。进入运行页后截图，以停止进程的方式丢弃临时会话，不点“结束”保存报告。
- 选择：首页、识谱 ACTIVE、和弦 ACTIVE、Practice Hub（含音程卡）、音程 ACTIVE。没有用缺少专属视觉的音程 Preparation 凑图。

## 无损展示优化

仅重新压缩 PNG 的 IDAT 数据。解压后的扫描线字节与全部非 IDAT 块分别逐字节一致；不缩放、不裁切、不降色、不覆盖文字、不调整色彩，也没有添加素材或重绘 UI。

| 页面 / 文件 | 原始 bytes | 展示 bytes |
| --- | ---: | ---: |
| [首页](bocchi-1.1.0-home.png) | 5786619 | 5496915 |
| [识谱练习](bocchi-1.1.0-sight-reading.png) | 492304 | 477618 |
| [和弦练习](bocchi-1.1.0-chord-practice.png) | 873822 | 819437 |
| [练习中心 / 音程卡](bocchi-1.1.0-interval-hub.png) | 4658766 | 4385881 |
| [音程练习](bocchi-1.1.0-interval-active.png) | 1134738 | 1092072 |

原始截图、采集命令、界面 XML 与优化一致性证据留存在本次仓库外验收报告目录，不进入 Git。

<details>
<summary>展示文件 SHA-256</summary>

| 文件 | SHA-256 |
| --- | --- |
| home | `5ceb7d695bf4266414b33a7e31d4c9912c58a188117928a7c350606bb869e6d1` |
| sight-reading | `78d40a971074a1a0c7b471c0f944348dd93234308b2a2e62e0dd69423125ec6b` |
| chord-practice | `f05739de3ba337e96acc1c3771d2d279d8e2c509eec5ddc0ee1c1b1e58fc0c0e` |
| interval-hub | `ff78dcfdd42e6171834a7c244c04ab44c13044ff2a895a720dce5613e302a8ea` |
| interval-active | `dc6401980c085ca9765d537f6122b22202fbafbc16f372018f28f83a9356c977` |

</details>

## 正式数据保护核对

采集前后，History 均为 **23 次练习、113 题**，可读取的历史界面信息一致；没有保存新会话。主要设置及识谱、和弦、音程设置前后核对一致，原主题保持 Bocchi 1.1.0，最终回到首页。

识谱：大谱表、C 大调、单音、调内音、100 题、固定 5 秒、隐藏音名。和弦：C 大调、20 题、显示构成音开启。音程：20 题、答案提示开启、低音升降号关闭。没有为截图调整这些选项。

一次未采用的音程取证画面出现错误反馈；未故意作答、未模拟输入，该临时会话已丢弃。重新取证的正式展示图为普通运行状态、已完成 0/20。

上述结论来自实机界面与设置核对，不代表对正式应用私有数据库进行过原始字节审计。运行时 MIDI 连接随进程启停变化，不视为持久化设置变化。
