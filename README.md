# intentdrift

**比较改写前后的查询意图，标出被悄悄换掉的目标。**

`intentdrift` —— 比对原查询与改写查询的核心意图，标出实体或目标被替换的情况

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`intentdrift.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install drnowhami-intentdrift
```

装完直接用命令名调用：

```bash
intentdrift --help
```

也可以不用安装，直接把 `intentdrift.py` 拷走用——它只依赖标准库。

## 为什么需要它

区分无害的同义改写与改变目标点的漂移

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 查询意图漂移 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python intentdrift.py --file input.txt
python intentdrift.py --text "示例内容"
python intentdrift.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 一致性靠字面差异判定，语义等价但写法不同会误报。
- 不解析跨文档的引用关系。

## 跑测试

```bash
python test_intentdrift.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/drnowhami/intentdrift>

---

## 关于作者

drnowhami 做查询意图漂移相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://drnowhami.github.io>
- 仓库：<https://github.com/drnowhami/intentdrift>

## 许可

MIT，见 [LICENSE](LICENSE)。
