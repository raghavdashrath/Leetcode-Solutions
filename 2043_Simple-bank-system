class Bank {
private: 
    bool isValid(int num){
        if(num > n || num<1) return false;
        return true;
    }
public:
    unordered_map<int, long long> mp;
    int n;
    Bank(vector<long long>& balance) {
        n = balance.size();
        for(int i=1; i<=balance.size(); i++){
            mp[i] = balance[i-1];
        }
    }
    
    bool transfer(int account1, int account2, long long money) {
        if(!isValid(account1) || !isValid(account2)){
            return false;
        }
        if(money>mp[account1]){
            return false;
        }
        else{
            mp[account2] += money;
            mp[account1] -= money;
            return true;
        }
    }
    
    bool deposit(int account, long long money) {
        if(!isValid(account)) return false;
        mp[account] += money;
        return true;
    }
    
    bool withdraw(int account, long long money) {
        if(money > mp[account] || !isValid(account)) return false;
        mp[account] -= money;
        return true;
    }
};