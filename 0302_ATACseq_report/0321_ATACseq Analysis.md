

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

|                                                              |     BM-0228-ATAC      |    G1ER-2H-0228-ATAC     |        HX-ATAC-5         | acceptable base line |
| :----------------------------------------------------------: | :-------------------: | :----------------------: | :----------------------: | :------------------: |
|                       **rawdata size**                       | 4.8G，about 76M reads | 2.77G，about 45.5M reads | 2.73G，about 38.4M reads |          -           |
|                      **cleandata size**                      |         3.35G         |           1.7G           |          2.12G           |          -           |
|                        alignment rate                        |        49.38%         |          15.88%          |          84.80%          |         80%          |
| non-duplicate, non-mitochondrial [aligned reads](https://www.encodeproject.org/data-standards/terms/#read-depth)(有效数据量) |          12M          |           4.5M           |           18M            |         50M          |

clean data General Statistics：

| Sample Name         | % Dups | % GC | Read Length | M Seqs |
| :------------------ | :----- | :--- | :---------- | :----- |
| BM-0228-ATAC_1      | 61.0%  | 45%  | 85 bp       | 37.0   |
| BM-0228-ATAC_2      | 62.0%  | 45%  | 85 bp       | 37.0   |
| G1ER-2H-0228-ATAC_1 | 32.0%  | 50%  | 69 bp       | 22.7   |
| G1ER-2H-0228-ATAC_2 | 33.2%  | 50%  | 68 bp       | 22.7   |
| HX-ATAC-5_1         | 39.3%  | 47%  | 104 bp      | 19.2   |
| HX-ATAC-5_2         | 39.6%  | 46%  | 104 bp      | 19.2   |

QC报告:https://github.com/sxqingwei/PRC2_ATACseq/blob/main/0302_ATACseq_report/add_info/cleandata_multiqc_report.html

## callpeak结果

|                       | Peaks Counts |
| :-------------------: | :----------: |
|   **BM-0228-ATAC**    |     2036     |
| **G1ER-2H-0228-ATAC** |     7744     |
|     **HX-ATAC-5**     |    11243     |
| **from Encode：G1E**  |    25095     |

**均使用macs2软件进行callpeak，参数相同，q-value取0.05**





## 生物学意义分析

### 对peaks进行相关基因注释，得到对应基因集

| Sample name       | Open GeneSets Name |
| ----------------- | ------------------ |
| BM-0228-ATAC      | **BM**             |
| G1ER-2H-0228-ATAC | **G1ER2H**         |
| HX-ATAC-5         | **5_WTR3**         |

### 1）和ENCODE上[G1E细胞系ATACseq](https://www.encodeproject.org/experiments/ENCSR280ZDP/)的开放基因对比：

![](0321_ATACseq Analysis.assets/venn1-16478782851604.png)

### 2）和R3在WT高表达的基因对比：

**R3_Hi: RNAseq结果中，WT_R3阶段表达量top1500的基因**



### 3）和R3在WT低表达的基因对比



### 4）和Muscle组织特异、neuro2a细胞特异表达基因对比：overlap较少，符合预期

**Muscle: 肌肉特异表达基因**



**neuro2a：小鼠神经母细胞瘤细胞系特异表达基因**



gene set from [PaGenBase](http://bioinf.xmu.edu.cn/PaGenBase/index.jsp)