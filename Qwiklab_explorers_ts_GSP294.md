# Introduction to APIs in Google Cloud || [GSP294](https://www.cloudskillsboost.google/focuses/3473?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

* ### Run the following Commands in CloudShell

```
# Authenticate and get the token
export OAUTH2_TOKEN=$(gcloud auth print-access-token)

export DEVSHELL_PROJECT_ID=$(gcloud config get-value project)

gcloud services enable storage.googleapis.com

gcloud config set project $DEVSHELL_PROJECT_ID


# Create the JSON file
cat > values.json << EOF
{
  "name": "${DEVSHELL_PROJECT_ID}-bucket",
  "location": "US",
  "storageClass": "MULTI_REGIONAL"
}
EOF

# Create the bucket
curl -X POST --data-binary @values.json \
    -H "Authorization: Bearer $OAUTH2_TOKEN" \
    -H "Content-Type: application/json" \
    "https://www.googleapis.com/storage/v1/b?project=$DEVSHELL_PROJECT_ID"

# Upload an image to the bucket
curl -X POST --data-binary @/home/gcpstaging25084_student/demo-image.png \
    -H "Authorization: Bearer $OAUTH2_TOKEN" \
    -H "Content-Type: image/png" \
    "https://www.googleapis.com/upload/storage/v1/b/${DEVSHELL_PROJECT_ID}-bucket/o?uploadType=media&name=demo-image.png"
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
