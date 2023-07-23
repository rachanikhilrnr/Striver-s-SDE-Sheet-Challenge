int Findposition(vector<int>& in,int inorderStart , int inorderEnd , int element ,int  n){
        for(int i = inorderStart; i <= inorderEnd; i++){
            if(in[i] == element){
                return i ; 
            }
        }
        return -1 ;
    }
    TreeNode<int> *solve(vector<int>& in, vector<int>& post,int &index, int inOrderStart,int inOrderEnd, int n){
          if(index < 0 || inOrderStart > inOrderEnd){
              return NULL;
          }
          int element = post[index--];
          TreeNode<int> *root = new TreeNode<int>(element);
          int position = Findposition(in , inOrderStart , inOrderEnd ,element, n);
          root -> right = solve(in,post,index,position + 1,inOrderEnd,n);
          root -> left = solve(in,post,index,inOrderStart,position - 1,n);
          return root;
    }
TreeNode<int>* getTreeFromPostorderAndInorder(vector<int>& post, vector<int>& in) 
{
	// Write your code here.
        int n = post.size();
        int postOrderIndex = n - 1;
        TreeNode<int> *ans = solve(in,post,postOrderIndex,0,n - 1,n);
        return ans;
}