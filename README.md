# array-codes
int longestSubarrayWithSumK(vector<int> a, long long k) {
    // Write your code here
    int i,j,l;
    long long s;
    s=0;
    i=0;j=0;l=0;
    while(j<a.size()){
      s=s+a[j];
      while(s>k&&i<=j)//here we are putting i<j bacause i andj are end of subarray so i should nt cross it,suppose iandj are at firstelement and ist element is> k so i will increae and become >j so we restrict that i shoul  increse but see that array should not end by crossing
      {
        s=s-a[i];
        i++;
      }
      if(s==k){
        l=max(l,j-i+1);
      }
      j++;
    }
    return l;
}
