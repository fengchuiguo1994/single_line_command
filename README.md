# single_line_command
我将把一些常用的单行命令记录下来
### perl
1.对于gencode(类似)的注释文件快速提取gene区间和基因的信息<br/>
`perl -lane 'if($F[2]eq"gene"){if(/gene_id "(.+?)\.\d+";.+?gene_type "(.+?)";.+?gene_name "(.+?)";/){print "$F[0]\t".($F[3]-1)."\t$F[4]\t$1\t.\t$F[6]\t$3\t$2"}}' gencode.vM23.annotation.gtf > mm10.info`<br/>
|染色体|起点|终点|基因ID|填位|正负链|基因name|注释类型|
```
chr1	3073252	3074322	ENSMUSG00000102693	.	+	4933401J01Rik	TEC
chr1	3102015	3102125	ENSMUSG00000064842	.	+	Gm26206	snRNA
```