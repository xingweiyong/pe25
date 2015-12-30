time<-list()
for(j in 1:5){
  ht<-readLines("http://www.pm25.com/tianjin.html",encoding = "UTF-8")
    #write.table(ht,"ht.txt")
  n1<-grep("全部监测点",ht)
  tianjin<-ht[n1:(n1+16)]
  temp=""
  for(i in 1:16){
    local<-substr(tianjin[i],(regexpr('mon',tianjin[i],T)+5),(regexpr('aqi',tianjin[i],T)-3))
    aqi<-substr(tianjin[i],(regexpr('aqi',tianjin[i],T)+5),(regexpr('pm25',tianjin[i],T)-3))
    pm25<-substr(tianjin[i],(regexpr('pm25',tianjin[i],T)+6),(regexpr('qua',tianjin[i],T)-3))
    lv<-substr(tianjin[i],(regexpr('qua',tianjin[i],T)+5),(regexpr('lv',tianjin[i],T)-3))
    temp<-rbind(temp,cbind(local,aqi,pm25,lv))
    
  }
  time[[j]]<-temp
  rm(ht,temp)
  Sys.sleep(600)
}
