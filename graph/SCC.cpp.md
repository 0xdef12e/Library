---
data:
  _extendedDependsOn:
  - icon: ':question:'
    path: template/template.cpp
    title: template/template.cpp
  _extendedRequiredBy: []
  _extendedVerifiedWith: []
  _isVerificationFailed: false
  _pathExtension: cpp
  _verificationStatusIcon: ':warning:'
  attributes:
    links: []
  bundledCode: "#line 2 \"template/template.cpp\"\n#include <bits/stdc++.h>\nusing\
    \ namespace std;\n#define ll long long\n#define rep(i, n) for (int i = 0; i <\
    \ n; i++)\n#define REP(i, n) for (int i = 1; i < n; i++)\n#define rev(i, n) for\
    \ (int i = n - 1; i >= 0; i--)\n#define REV(i, n) for (int i = n - 1; i > 0; i--)\n\
    #define all(v) v.begin(), v.end()\n#define PL pair<ll, ll>\n#define PI pair<int,\
    \ int>\n#define pi acos(-1)\n#define len(s) (int)s.size()\n#define compress(v)\
    \ \\\n    sort(all(v));   \\\n    v.erase(unique(all(v)), v.end());\n#define comid(v,\
    \ x) lower_bound(all(v), x) - v.begin()\n\ntemplate<class T>\nusing prique=priority_queue<T,vector<T>,greater<>>;\n\
    \ntemplate <class T, class U>\ninline bool chmin(T &a, U b) {\n    if (a > b)\
    \ {\n        a = b;\n        return true;\n    }\n    return false;\n}\ntemplate\
    \ <class T, class U>\ninline bool chmax(T &a, U b) {\n    if (a < b) {\n     \
    \   a = b;\n        return true;\n    }\n    return false;\n}\nconstexpr ll inf\
    \ = 3e18;\n#line 3 \"graph/SCC.cpp\"\n\nstruct SCC {\n    vector<vector<ll>> G,\
    \ rG;\n    vector<bool> used;\n    vector<ll> vs;\n    void addEdge(ll x, ll y)\
    \ {\n        G[x].push_back(y);\n        rG[y].push_back(x);\n    }\n    void\
    \ dfs(ll x) {\n        used[x] = true;\n        for (ll i : G[x])\n          \
    \  if (!used[i]) dfs(i);\n        vs.push_back(x);\n    }\n    vector<ll> cmp;\n\
    \    void rdfs(ll v, ll k) {\n        used[v] = true;\n        cmp[v] = k;\n \
    \       for (ll i : rG[v])\n            if (!used[i]) rdfs(i, k);\n    }\n   \
    \ void scc() {\n        fill(all(used), false);\n        rep(i, len(G)) if (!used[i])\
    \ dfs(i);\n        fill(all(used), false);\n        ll k = 0;\n        rev(i,\
    \ len(vs)) if (!used[vs[i]]) rdfs(vs[i], k++);\n    }\n    SCC(ll N) : G(N), rG(N),\
    \ used(N), cmp(N) {}\n};\n"
  code: "#pragma once\n#include \"../template/template.cpp\"\n\nstruct SCC {\n   \
    \ vector<vector<ll>> G, rG;\n    vector<bool> used;\n    vector<ll> vs;\n    void\
    \ addEdge(ll x, ll y) {\n        G[x].push_back(y);\n        rG[y].push_back(x);\n\
    \    }\n    void dfs(ll x) {\n        used[x] = true;\n        for (ll i : G[x])\n\
    \            if (!used[i]) dfs(i);\n        vs.push_back(x);\n    }\n    vector<ll>\
    \ cmp;\n    void rdfs(ll v, ll k) {\n        used[v] = true;\n        cmp[v] =\
    \ k;\n        for (ll i : rG[v])\n            if (!used[i]) rdfs(i, k);\n    }\n\
    \    void scc() {\n        fill(all(used), false);\n        rep(i, len(G)) if\
    \ (!used[i]) dfs(i);\n        fill(all(used), false);\n        ll k = 0;\n   \
    \     rev(i, len(vs)) if (!used[vs[i]]) rdfs(vs[i], k++);\n    }\n    SCC(ll N)\
    \ : G(N), rG(N), used(N), cmp(N) {}\n};\n"
  dependsOn:
  - template/template.cpp
  isVerificationFile: false
  path: graph/SCC.cpp
  requiredBy: []
  timestamp: '2021-09-12 23:44:25+09:00'
  verificationStatus: LIBRARY_NO_TESTS
  verifiedWith: []
documentation_of: graph/SCC.cpp
layout: document
redirect_from:
- /library/graph/SCC.cpp
- /library/graph/SCC.cpp.html
title: graph/SCC.cpp
---