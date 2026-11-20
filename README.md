# AI 时代下的搜索技术——以 RAG 为例

课程项目比较三种搜索动作：给链接、基于已取得的证据作答、为缺失的证据定向补搜。模拟实验覆盖导航、单项查询、双对象比较和当前资料不足。

- [课程报告](课程报告.md)
- [搜索技术演变史完整对话](chat/搜索技术演变史_完整对话.md)
- [实验脚本](experiment.py)、[结果统计](results/summary.csv)、[逐题结果](results/by_query.csv)、[运行与反例记录](results/run.json)

## 复现

Python 3.10+，仅需标准库。

```bash
python experiment.py --out replay
```

脚本从固定种子生成合成文档和 102 个问题，回放两种语料视图下的六种策略，输出 1,224 条逐题记录。将 CSV 的 SHA-256 与 [run.json](results/run.json) 对照即可核查。语料文件 [corpus.json.gz](results/corpus.json.gz) 是可解压的 JSON。原型使用 BM25 与固定模板。
