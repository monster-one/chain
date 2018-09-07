
Transactions：
发送Times到某个账号ID接口：
/api/transactions:
"get /": "获取某交易列表，最近1000条 如：http://host:7000/api/transactions",

"get /get": "获取某条交易记录 如：http://host:7000/api/transactions/get?id=3095726577455238661",

"get /unconfirmed/get": "获取某条未确认交易",

"get /unconfirmed": "获取未确认的交易列表如： /api/transactions/unconfirmed",

"put /": "发送一次交易如下面示例：" 

var data = {
    secret: "xxx", //发送人持有的主密码
    secondSecret : "xxx", //发送人的二次密码
    amount: 1000,      //发送的数量
    recipientId: "xxx",  //收ID的地址
    publicKey: "xxx"   //公钥
};


request({
    url: "http://host:7000/api/transactions", //host：节点服务器地址
    method: "PUT",
    json: true,
    headers: {
        "content-type": "application/json",
    },
        body: JSON.stringify(data)
    }, function(error, response, body) {
        console.log(error);
        console.log(response);
        console.log(body);
        if (!error && response.statusCode == 200) {
        }
}); 


查看节点接口：
/api/peers


账户相关接口：
/api/accounts:

"post /open": "开一个账户如：",
var data = {
    secret: "12", //发送人持有的主密码
};

request({
    url: "http://host:7000/api/accounts/open", //host：节点服务器地址
    method: "POST",
    json: true,
    headers: {
        "content-type": "application/json",
    },
        body: JSON.stringify(data)
    }, function(error, response, body) {
        
    }
});
返回：
{ success: true,
  account: 
   { address: '17649443584386761059L',
     unconfirmedBalance: 0,
     balance: 0,
     publicKey: '571f06ced49c35c93c47a662a441d7ab7b3c810d0dc3c4e86bb41cd22a77657f',
     unconfirmedSignature: false,
     secondSignature: false,
     secondPublicKey: '',
     multisignatures: [],
     u_multisignatures: [] } }

"get /getBalance": "获取某个地址对应的账户余额：/api/accounts/getBalance?address=17796021780951493822L",
"get /getPublicKey": "获取某个账号的Public Key：/api/accounts/getPublicKey?address=9635694465406141212L",
"post /generatePublicKey": "生成一个公钥",
var data = {
    secret: "123", //发送人持有的主密码
};

request({
    url: "http://host:7000/api/accounts/open", //host：节点服务器地址
    method: "POST",
    json: true,
    headers: {
        "content-type": "application/json",
    },
        body: JSON.stringify(data)
    }, function(error, response, body) {
        
    }
});
{ success: true,
  publicKey: 'a4465fd76c16fcc458448076372abf1912cc5b15021263a64dffefe550f96feadd' }

"get /delegates": "获取代理列表",
"get /delegates/fee": "获取成为一个代理的费用",
"put /delegates": "增加一个代理",
"get /username/get": "获取某个账号情况：",
"get /username/fee": "获取生成用户名的费用",
"put /username": "增加用户名",
"get /": "获取某个账号情况：/api/accounts?address=17796021780951493822L"



区块相关接口：
/api/blocks:
"get /get": "获取某个区块 如： /api/blocks/get?id=1740263798890688801",
"get /": "获取区块列表 如：/api/blocks",
"get /getHeight": "获取某个区块高度",
"get /getFee": "获取某个区块交易费",
"get /getMilestone": "获取某个区块里程",
"get /getReward": "获取奖励",
"get /getSupply": "获取当前提供的总量",
"get /getStatus": "获取当前状态 返回结果：{"success":true,"height":16136,"fee":10000000,"milestone":0,"reward":0,"supply":10000000000000000}"








