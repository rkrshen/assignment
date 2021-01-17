


nslookup

DNS=解析網站ＩＰ


http 的server

http.createServer(aaa)
function aaa(req,res){
    console.log(req.url)
    if(req.url ==='/'){
        res.write('haha')
        res.end()
        return
    }
    if(req.url ==='/redirect'){
        res.writeHead(302,{
            'Location': 'https://www.google.com'
        })
        res.end()
        return
    }

}
server.listen(5000) //port