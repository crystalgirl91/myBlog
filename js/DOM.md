NodeList和 HTMLCollection对象不是历史文档状态的一个静态快照，他通常是实时更新的，并且当文档变化时，
他们所包含的元素列表能随之改变，这是一个重要的特性。假设在一个没有<div>元素的文档中调用
document.getElementsByTagName("div"),此时将返回一个lenth值为0 的NodeList对象，如果再在文档中
插入一个新的 <div>对象，则NodeList对象将自动更新成员变化，lenth长度为1。

###Element对象选取

Element对象的Children属性，类似childeNodes,它是一个NodeList对象，但不同的是children
列表只包含Element对象，不包括Text和Comment对象。
Text 和 Commnet的节点没有children属性。

firstElementChild,lastElementChild
	类似于firstChild,lastChild,但是只表示字Element

nextElementSibling,previousElementSibling,
	类似nextSibling,previousSibling,单只表示兄弟Element

childrenElemntCount
	子元素的数量，返回值和children.length值相等

Node类型定义了Attributes属性，但只有Element对象有效。类似NodeList,Attributes对象也是实时的。
