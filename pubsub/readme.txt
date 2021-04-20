gcloud auth list
gcloud config list project


# install python venv
sudo apt-get update
sudo apt-get install virtualenv

virtualenv -p python venv
source venv/bin/activate

# install the client library
pip install --update google-cloud-pubsub
git clone https://github.com/googleapis/python-pubsub.git
cd python-pubsub/samples/snippets

export GLOBAL_CLOUD_PROJECT=<project id>

python publisher.py -h

# Create Topic and Subscription
python publisher.py $GLOBAL_CLOUD_PROEJCT create MyTopic

python publisher.py $GLOBAL_CLOUD_PROJECT list

python subscriber.py $GLOBAL_CLOUD_PROJECT create MyTopic MySub

python subscriber.py $GLOBAL_CLOUD_PROJECT list-in-proejct

# Publish Messages

gcloud pubsub topics publish MyTopic --message "Hello"
gcloud pubsub topics publish MyTopic --message "Publisher's name is Myname"

# Check the messages
python subscriber.py $GLOBAL_CLOUD_PROEJCT receive MySub

