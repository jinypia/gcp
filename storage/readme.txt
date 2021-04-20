# Create a bucket

gsutil mb gs://superarchi-bucket/

wget --output-document ada.jpg https://<-- image page -->

gsutil cp ada.jpg gs://superarchi-bucket

# Download an object
gsutil cp -r gs://superarchi-bucket/ada.jpg .

gsutil cp gs://superarchi-bucket/ada.jpg gs://sueprarchi-bucket/image-folder/

gsutil ls gs://superarchi-bucket

gsutil ls -l gs://superarchi-bucket/ada.jpg

# Make the object publicly accessible
gsutil acl ch -u AllUsers:R gs://superarchi-bucket/ada.jpg

# Delete the permission
gsutil acl ch -d AllUsers:R gs://superarchi-bucket/ada.jpg

gsutil rm gs://superarchi-bucket/ada.jpg

