class Solution {
public:
    vector<vector<int>> bfs(vector<vector<int>>& heights, int type){
        int n = heights.size();
        int m = heights[0].size();
        vector<vector<int>> used(n, vector<int>(m));
        queue<pair<int,int>> q;
        for(int i=0; i<n; i++){
            for(int j=0; j<m; j++){
                if(type == 0 && (i == 0 || j == 0)){
                    q.push({i,j});
                    used[i][j] = 1;
                }
                if(type == 1 && (i == n-1 || j == m-1)){
                    q.push({i,j});
                    used[i][j] = 1;
                }
            }
        }

        vector<int> row = {1,0,0,-1};
        vector<int> col = {0,1,-1,0};

        while(!q.empty()){
            int r = q.front().first;
            int c = q.front().second;
            q.pop();

            for(int i=0; i<4; i++){
                int nr = r + row[i];
                int nc = c + col[i];
                if(nr >= 0 && nr < n && nc >= 0 && nc < m 
                   && !used[nr][nc] && heights[r][c] <= heights[nr][nc]){
                    used[nr][nc] = 1;
                    q.push({nr,nc});
                }
            }
        }
        return used;
    }
    
    vector<vector<int>> pacificAtlantic(vector<vector<int>>& heights) {
        vector<vector<int>> usedp = bfs(heights,0);
        vector<vector<int>> useda = bfs(heights,1);
        vector<vector<int>> ans;

        int n = heights.size();
        int m = heights[0].size();

        for(int i=0; i<n; i++){
            for(int j=0; j<m; j++){
                if(usedp[i][j] && useda[i][j]){
                    ans.push_back({i,j});
                }
            }
        }
        return ans;
    }
};