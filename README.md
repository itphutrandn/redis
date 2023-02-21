# REDIS NOTE

## Basic Command
![image](https://user-images.githubusercontent.com/71063877/220327920-738dc46b-442a-41f6-8543-30344981efc2.png)

### Commands for Handlings Strings
![image](https://user-images.githubusercontent.com/71063877/220328641-d3a25a05-23e3-43fb-89f9-eb2b6d9da460.png)

![image](https://user-images.githubusercontent.com/71063877/220328763-988af1ca-e08c-4138-a232-1cd70b2a0b99.png)

![image](https://user-images.githubusercontent.com/71063877/220328845-c624c47d-cc42-4b47-b00f-933581b1336c.png)

Please refer to the link bellow:
https://redis.io/commands/

### Json demo:

{
  "name": "Basic Strings",
  "fileName": "My Easy Amount Notebook.json",
  "createdAt": "2022-03-08T21:22:37.931Z",
  "cells": [
    {
      "id": "1646934030950",
      "type": "markdown",
      "content": "Commands are used to fetch or query data. All data is stored into key value pairs. A value can be a simple string or a more complicated data structure like a list or a hash table.\n\nTo set a key value pair with a simple string value, use the SET command. \n1. The first argument to SET is the name of the key we wish to set\n2. The second argument is the string we wish to save\n\nIf the string has any spaces, we must wrap the string with single or double quotes."
    },
    {
      "id": "02487ea365afcf4d",
      "type": "redis",
      "content": "SET message 'Hi there!'"
    },
    {
      "id": "1646934130113",
      "type": "markdown",
      "content": "A value can be retrieved from the database using the GET command."
    },
    {
      "id": "1646845987401",
      "type": "redis",
      "content": "GET message"
    },
    {
      "id": "1646934151982",
      "type": "markdown",
      "content": "There are many, many variations of the SET command.\n\nFor example, you can use the GET keyword at the end of a SET. Doing so will change the value of the key, then return the old value."
    },
    {
      "id": "1646848749447",
      "type": "redis",
      "content": "SET color red\n\nSET color green GET"
    },
    {
      "id": "1646934205960",
      "type": "markdown",
      "content": "The XX argument will set a key only if it already references a value"
    },
    {
      "id": "1646849498559",
      "type": "redis",
      "content": "SET color 'hi there' XX"
    },
    {
      "id": "1646934235674",
      "type": "markdown",
      "content": "The NX argument will cause the SET to run only if the key does not reference a value"
    },
    {
      "id": "1646849557790",
      "type": "redis",
      "content": "SET colorlaksjdf blue NX"
    },
    {
      "id": "1646934263711",
      "type": "markdown",
      "content": "Many variations of the SET command allow you to automatically 'expire', or delete, a value after a period of time.\n\nThe EX argument will delete the value after the stated number of seconds. In the example below, color will be deleted automatically after two seconds."
    },
    {
      "id": "1646849656483",
      "type": "redis",
      "content": "SET color red EX 2\n\nGET color"
    },
    {
      "id": "1646934322255",
      "type": "markdown",
      "content": "Continuation of the example above - run this GET color after two seconds, and you'll get back null, even though we had set color just a moment ago."
    },
    {
      "id": "1646852666865",
      "type": "redis",
      "content": "GET color"
    },
    {
      "id": "1646934351324",
      "type": "markdown",
      "content": "The SET command takes many optional arguments to adjust how it works. There are also standalone versions of SET that automatically include these optional arguments.\n\nThe SETEX command, for example, is identical to using SET with the EX option."
    },
    {
      "id": "1646853718158",
      "type": "redis",
      "content": "SETEX color 2 red"
    },
    {
      "id": "1646934407482",
      "type": "markdown",
      "content": "MSET can be used to set multiple key-value pairs at the same time."
    },
    {
      "id": "1646853758671",
      "type": "redis",
      "content": "MSET color red model toyota\n\nGET color\nGET model"
    },
    {
      "id": "1646934429931",
      "type": "markdown",
      "content": "MGET is the companion to MSET - it will fetch the values of multiple different keys with a single command."
    },
    {
      "id": "1646854038228",
      "type": "redis",
      "content": "MGET color model"
    },
    {
      "id": "1646934448317",
      "type": "markdown",
      "content": "DEL is used to remove a key-value pair. It can be used on any key, not just keys that reference strings."
    },
    {
      "id": "1646854409220",
      "type": "redis",
      "content": "GET color\n\nDEL color\n\nGET color"
    },
    {
      "id": "1646934467308",
      "type": "markdown",
      "content": "GETRANGE returns a series of characters out of an existing string. \n\nArguments:\n1. The key we want to look up\n2. The start index of the range\n3. The end index (inclusive) of the range\n\nThe index values should be zero based. That is, the first character of the string is index 0."
    },
    {
      "id": "1646856685259",
      "type": "redis",
      "content": "GET model\n\nGETRANGE model 0 2"
    },
    {
      "id": "1646934515387",
      "type": "markdown",
      "content": "SETRANGE is the companion to GETRANGE.\n\nArguments:\n1. The key we wish to modify\n2. The index of the first character we want to overwrite\n3. The string that will be written into the existing one\n\nNote that this isn't an insert operation. SETRANGE will overwrite existing characters."
    },
    {
      "id": "1646856748933",
      "type": "redis",
      "content": "SETRANGE model 2 blue\n\nGET model"
    },
    {
      "id": "1646934596792",
      "type": "markdown",
      "content": "Many string commands can be use with numbers as well. Redis doesn't have a separate type for numbers. When retrieving a number value with the GET command, it is up to your application to parse the string into a number."
    },
    {
      "id": "1646931821375",
      "type": "redis",
      "content": "SET age 20\n\nGET age // returns a string"
    },
    {
      "id": "1646934659816",
      "type": "markdown",
      "content": "INCR will increase a number by exactly one."
    },
    {
      "id": "1646934673881",
      "type": "redis",
      "content": "INCR age"
    },
    {
      "id": "1646934681032",
      "type": "markdown",
      "content": "DECR will decrease a number by exactly one."
    },
    {
      "id": "1646932290963",
      "type": "redis",
      "content": "DECR age"
    },
    {
      "id": "1646934689612",
      "type": "markdown",
      "content": "INCRBY will increase a number by the amount provided.\n\nDECRBY will increase a number by the amount provided."
    },
    {
      "id": "1646932326062",
      "type": "redis",
      "content": "INCRBY age 20\n\nDECRBY age 4"
    },
    {
      "id": "1646934700241",
      "type": "markdown",
      "content": "All of the previous commands worked with integers. \n\nINCRBYFLOAT is used when we want to add or subtract a number with a decimal component."
    },
    {
      "id": "1646932375806",
      "type": "redis",
      "content": "INCRBYFLOAT age -3.333"
    }
  ],
  "id": "a2f6ea45ceda3b22"
}



