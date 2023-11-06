import requests
import json

url="https://thrillshare-cmsv2.services.thrillshare.com/api/v4/o/[SCHOOL_ID]/cms/directories?locale=en&filter_ids="
limit = 29
page = 1
content = []

while page <= limit:
    response = requests.get(url + "&page_no=" + str(page))
    content.append(response.text)
    page = page + 1

first = 1
for x in content:
    if first == 1:
        first = 0
        a = json.loads(x)
    else:
        b = json.loads(x)
        a['directories'].append(b['directories'])
        #print(a)

with open('GetStaffDirectory.output.txt', 'w') as f:
    f.write(json.dumps(a))
