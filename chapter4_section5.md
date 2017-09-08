# 大量数据场景下快速、丰富的数据检索服务

该方案使用lucene反向索引检索技术，提供快速、丰富的的数据检索能力。
数据检索能力包括但不限于：

<table>
   <tr>
      <td>分词类型</td>
      <td>说明</td>
   </tr>
   <tr>
      <td>模糊分词</td>
      <td>类似于数据库的全模糊搜索，如果字段包含任何查询条件的内容，将返回该条记录</td>
   </tr>
   <tr>
      <td>前缀匹配</td>
      <td>类似于数据库的右模糊搜索，基于查询条件的前缀匹配</td>
   </tr>
   <tr>
      <td>拼音分词</td>
      <td>支持简拼，全拼的模糊匹配分词</td>
   </tr>
   <tr>
      <td>IK分词</td>
      <td>基于IK分词的自然语义的分词模型</td>
   </tr>
   <tr>
      <td>英文分词</td>
      <td>基于英文模型的分词，按照空格，标点分词</td>
   </tr>
   <tr>
      <td>英文去词根分词</td>
      <td>在英文模型分词的基础上，将复词转换为词根</td>
   </tr>
   <tr>
      <td>不分词</td>
      <td>对原始词不分词，需要搜索条件全匹配</td>
   </tr>
</table>