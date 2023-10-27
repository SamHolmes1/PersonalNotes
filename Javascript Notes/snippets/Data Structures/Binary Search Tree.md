```js
function createNode(data, left=null, right=null){
	return{
		data: data,
		left: left,
		right: right
	}
}

function createTree() {
	let returnTree = Object.create(treePrototype)
	returnTree.root = null
	return returnTree;
}

const treePrototype = {
	add: function add(data){
		const node = this.root;
		if (node === null) {
			console.log("Created Root")
			this.root = createNode(data)
		}else{
			const drillTree = function(node){
				if(data > node.data){
					if(node.right === null){
						console.log("Larger")
						node.right = createNode(data)
					}
					else if(node.right !== null){
						console.log("larger recursion")
						drillTree(node.right, data)
					}
				}
				else if (data < node.data){
					if(node.left === null){
						console.log("Smaller")
						node.left = createNode(data)
					}
					else if(node.left !== null){
						console.log("smaller recursion")
						drillTree(node.left, data)
					}
				}else{
					return null;
				}
			}
			drillTree(node)
		}
	},
}
module.exports = createTree;
```