Search in a 2d Matrix
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {
        for(int i=0;i<matrix.size();i++){
            if(binary_search(matrix[i].begin(),matrix[i].end(),target)){
                return true;
            }
        }
        return false;
    }
};
Pow(X,n)
class Solution {
public:
    double myPow(double x, int n) {
        long a = n;
        double ans = 1.0;
        if(a<0) a = -1*a;       //if power is negative make it positive, for simplicity
        while(a>0){
            if(a%2==0){     //checking if power is even
                x = x*x;    //if even, suppose 2^4, do (2*2)^2, diving problem in simpler steps.
                a = a/2;        //divide power by 2
            }
            else{           //if power is odd
                ans = ans*x;    //if odd, suppose 2^5, do (2^4)*2, to break it down into even power
                a = a-1;        //decrease n 
            }
        }
        if(n<0)    ans = (double)(1.0)/(double)(ans);    //the reason for doing (-1*a), if n is negative power, simply move the answer in denominator
        return ans;            
    }
};
Majority Element (>N/2 times)
class Solution {
public:
    int majorityElement(vector<int>& nums) {
       int c=0;
        int ans=0;
        for(int i:nums){
            if(c==0){
                ans=i;
            }
            if(i==ans){
                c++;
            }else{
                c--;
            }
        }
        return ans;
    }
};
62. Unique Paths
class Solution {
public:
   
    int uniquePaths(int m, int n) {
        int dp[m][n];
        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
                dp[i][j]=1;
            }
        }
        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
                if(i==0 || j==0){
                    dp[i][j]=1;
                }else{
                dp[i][j]=dp[i][j-1]+dp[i-1][j];
                }
            cout<<dp[i][j]<<" ";
            }
           cout<<endl;
        }
          return dp[m-1][n-1]; 
    }
};
reverse pairs ?
