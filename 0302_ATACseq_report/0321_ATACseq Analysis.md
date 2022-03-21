

# ATACseq Data Analysis

## 样品信息

|       样本名称       |   BM-0228-ATAC   | G1ER-2H-0228-ATAC |    HX-ATAC-5     |
| :------------------: | :--------------: | :---------------: | :--------------: |
|       样本编号       | FKDL220019772-1a | FKDL220019773-1a  | FKDL220011795-1a |
|       细胞类型       |        BM        |        G1E        |      WT-R3       |
|      分选细胞数      |                  |                   |                  |
|      分选回测率      |                  |                   |                  |
|   Peak size（bp）    |                  |                   |                  |
| QPCR摩尔浓度(nmol/L) |                  |                   |                  |
|       峰图描述       |                  |                   |                  |
|     库检综合结果     |                  |                   |                  |

**qc文库峰图：**

BM-0228-ATAC

G1ER-2H-0228-ATAC

HX-ATAC-5

## 比对结果

**流程：rawdata进行去接头、过滤低质量序列，得到clean data；将clean data比对到小鼠参考基因组（mm10）；再将比对上的序列去除PCR重复和线粒体基因，得到有效数据进行下游分析**

clean data General Statistics：



|                                                              |     BM-0228-ATAC      |    G1ER-2H-0228-ATAC     |        HX-ATAC-5         | acceptable base line |
| :----------------------------------------------------------: | :-------------------: | :----------------------: | :----------------------: | :------------------: |
|                       **rawdata size**                       | 4.8G，about 76M reads | 2.77G，about 45.5M reads | 2.73G，about 38.4M reads |          -           |
|                      **cleandata size**                      |         3.35G         |           1.7G           |          2.12G           |          -           |
|                        alignment rate                        |        49.38%         |          15.88%          |          84.80%          |         80%          |
| non-duplicate, non-mitochondrial [aligned reads](https://www.encodeproject.org/data-standards/terms/#read-depth)(有效数据量) |          12M          |           4.5M           |           18M            |         50M          |

## callpeak结果

|                       | Peaks Counts |
| :-------------------: | :----------: |
|   **BM-0228-ATAC**    |              |
| **G1ER-2H-0228-ATAC** |              |
|     **HX-ATAC-5**     |              |
| **from Encode：G1E**  |    25095     |

**均使用macs2软件进行callpeak，参数相同，q-value取0.05**

## 生物学意义分析

### 对peaks进行相关基因注释，得到基因集（mut_R2_gene），将其分别

### 1）和ENCODE上[G1E细胞系ATACseq](https://www.encodeproject.org/experiments/ENCSR280ZDP/)的开放基因对比：

![](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/1.png)

### 2）和R2在WT、Mut均高表达的基因对比：overlap较少

**R2_Hi: RNAseq结果中，WT_R2,Mut_R2阶段表达量top1500的基因交集**

![3](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/3.png)

![6](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/6.png)

### 3）和R2在WT、Mut均无表达的基因对比

**R2_none: RNAseq结果中，WT_R2,Mut_R2表达量为零（fpkm=0）的基因交集**

![5](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/5.png)

![7](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/7.png)

### 4）和R2在WT、Mut均低表达的基因对比

**R2_low: RNAseq结果中，WT_R2,Mut_R2表达量低（fpkm<0.1）的基因交集**

![2](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/2.png)

### 5）和Muscle组织特异、neuro2a细胞特异表达基因对比：overlap较少，符合预期

**Muscle: 肌肉特异表达基因**

![4](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/4.png)

**neuro2a：小鼠神经母细胞瘤细胞系特异表达基因**

![](https://github.com/sxqingwei/PRC2_ATACseq/raw/main/add_info/8.png)

gene set from [PaGenBase](http://bioinf.xmu.edu.cn/PaGenBase/index.jsp)