# upload-iii-Repo


import time
i=0

# print "start ----" + datetime.now().strftime('%H%M%S')
while True:
    try:
        i +=1
        with open('TRAFFIC/traffic'+datetime.now().strftime('%Y%m%d')+datetime.now().strftime('%H%M%S'),'w') as f:
                base_url ='http://data.taipei/opendata/datalist/apiAccess?scope=resourceAquire&rid=5aacba65-afda-4ad5-88f5-6026934140e6'

                res=requests.get(base_url)
                soup=bs(res.text,'html5lib')
                #print (soup.text)
                f.write(soup.text.encode('utf-8'))
                

                time.sleep(360)
                if i<0:
                    break
    except  IOError as e:
        print (e.args[1])

    finally:
        
        f.close()
#         print datetime.now().strftime('%H%M%S')
