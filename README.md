# 谱析 Research

一个可复现的贝多芬钢琴奏鸣曲曲式分析研究基线：

- 只接收未压缩的 `.musicxml` / `.xml`；
- 使用 OpenSheetMusicDisplay 2.2.1 排谱；
- 使用 Taking Form 的 32 首贝多芬奏鸣曲、103 个乐章人工标注作为真值；
- 将人工标注、自动预测和评价指标明确分开；
- 自动基线目前只预测呈示部、展开部、再现部，不声称已自动识别主部、连接部、副部。

## 重建语料数据

```sh
node scripts/build-taking-form-data.mjs \
  /path/to/Taking-Form/corpus/Beethoven_Sonatas \
  dist/data/taking-form-beethoven.json
```

## 本地预览

```sh
python3 -m http.server 4173 --directory dist
```

然后访问 `http://127.0.0.1:4173`。

## 数据与许可证

- [Taking Form](https://github.com/MarkGotham/Taking-Form)，MIT
- [OpenSheetMusicDisplay](https://github.com/opensheetmusicdisplay/opensheetmusicdisplay)，BSD-3-Clause

第三方说明见 `dist/vendor/NOTICE.txt`。
