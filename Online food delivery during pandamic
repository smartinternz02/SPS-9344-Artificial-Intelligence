# SPS-9344-Artificial-Intelligence
Artificial Intelligence
Update credentials
import json
from ibm_watson import AssistantV1
from ibm_cloud_sdk_core.authenticators import IAMAuthenticator

authenticator = IAMAuthenticator('')
assistant = AssistantV1(
            version='2018-07-10',
            authenticator=authenticator)
assistant.set_service_url('')
workspace_id = ''
Create Intent
examples = [{"text": "good morning"}]
response = assistant.create_intent(
    workspace_id=workspace_id,
    intent='test_intent',
    description='Test intent.',
    examples=examples).get_result()
print(json.dumps(response, indent=2))

response = assistant.get_intent(
    workspace_id=workspace_id, intent='test_intent', export=True).get_result()
print(json.dumps(response, indent=2))
{
  "intent": "test_intent",
  "description": "Test intent."
}
{
  "intent": "test_intent",
  "examples": [
    {
      "text": "good morning"
    }
  ],
  "description": "Test intent."
}
List intents
In [3]:
response = assistant.list_intents(
    workspace_id=workspace_id, export=True).get_result()
print(json.dumps(response, indent=2))
{
  "intents": [
    {
      "intent": "covid",
      "examples": [
        {
          "text": "Latest news on Covid"
        },
        {
          "text": "I want to know more about Covid"
        },
        {
          "text": "Covid-19"
        },
        {
          "text": "What is Covid"
        },
        {
          "text": "Corona Virus"
        }
      ],
      "description": "know more about Covid-19"
    },
    {
      "intent": "order",
      "examples": [
        {
          "text": "order"
        },
        {
          "text": "I would like to place the order"
        },
        {
          "text": "Place the order"
        },
        {
          "text": "I want to place the order"
        },
        {
          "text": "I need to place an order"
        }
      ],
      "description": ""
    },
    {
      "intent": "stop",
      "examples": [
        {
          "text": "That's it"
        },
        {
          "text": "I am done"
        },
        {
          "text": "Nothing else"
        },
        {
          "text": "This is all"
        },
        {
          "text": "not now"
        },
        {
          "text": "no"
        },
        {
          "text": "I will get back later"
        },
        {
          "text": "not ready"
        },
        {
          "text": "thats it"
        },
        {
          "text": "nothing"
        },
        {
          "text": "That is it"
        }
      ],
      "description": ""
    },
    {
      "intent": "test_intent",
      "examples": [
        {
          "text": "good morning"
        }
      ],
      "description": "Test intent."
    }
  ],
  "pagination": {
    "refresh_url": "/instances/b7500039-8431-48b0-8af7-d6cae088f217/v1/workspaces/977f8c02-24cf-4f6f-9411-978e79f643d4/intents?version=2018-07-10&export=true"
  }
}
Update intent
In [4]:
response = assistant.update_intent(
    workspace_id=workspace_id,
    intent='test_intent',
    new_intent='updated_test_intent',
    new_description='Updated test intent.').get_result()
print(json.dumps(response, indent=2))
{
  "intent": "updated_test_intent",
  "description": "Updated test intent."
}
Delete intent
In [5]:
response=assistant.delete_intent(
    workspace_id=workspace_id,
    intent='updated_test_intent'
).get_result()

print(json.dumps(response, indent=2))
{}
Create entity
In [6]:
response=assistant.create_entity(
    workspace_id=workspace_id,
    entity='Location',
    values=[
        {'value': 'US'},
        {'value': 'India'},
        {'value': 'UK'}
    ]
).get_result()

print(json.dumps(response, indent=2))
{
  "entity": "Location"
}
Update entity
In [7]:
response=assistant.update_entity(
    workspace_id=workspace_id,
    entity='Location',
    new_values=[
        {'value': 'Germany'},
        {'value': 'Brazil'},
        {'value': 'Spain'}
    ],
    append="true",
    include_audit="true",
    new_description='updated data').get_result()
print(json.dumps(response, indent=2))
{
  "entity": "Location",
  "created": "2020-08-20T09:20:21.631Z",
  "updated": "2020-08-20T09:20:22.019Z",
  "description": "updated data"
}
List the entities
In [8]:
response = assistant.list_entities(workspace_id=workspace_id).get_result()
print(json.dumps(response, indent=2))
{
  "entities": [
    {
      "entity": "covid",
      "fuzzy_match": true
    },
    {
      "entity": "Location",
      "description": "updated data"
    },
    {
      "entity": "products",
      "fuzzy_match": true
    },
    {
      "entity": "stop",
      "fuzzy_match": true
    }
  ],
  "pagination": {
    "refresh_url": "/instances/b7500039-8431-48b0-8af7-d6cae088f217/v1/workspaces/977f8c02-24cf-4f6f-9411-978e79f643d4/entities?version=2018-07-10"
  }
}
Delete entity
In [9]:
response=assistant.delete_entity(
    workspace_id=workspace_id,
    entity='Location'
).get_result()

print(json.dumps(response, indent=2))
{}
In [10]:
response = assistant.list_entities(workspace_id=workspace_id).get_result()
print(json.dumps(response, indent=2))
{
  "entities": [
    {
      "entity": "covid",
      "fuzzy_match": true
    },
    {
      "entity": "products",
      "fuzzy_match": true
    },
    {
      "entity": "stop",
      "fuzzy_match": true
    }
  ],
  "pagination": {
    "refresh_url": "/instances/b7500039-8431-48b0-8af7-d6cae088f217/v1/workspaces/977f8c02-24cf-4f6f-9411-978e79f643d4/entities?version=2018-07-10"
  }
}
