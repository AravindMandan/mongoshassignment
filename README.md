# mongoshassignment
show dbs
admin       40.00 KiB
config      60.00 KiB
local       40.00 KiB
mydatabase   8.00 KiB

use mydb
switched to db mydb

db.tasks.insertOne({})
{
  acknowledged: true,
  insertedId: ObjectId('6836dff71f69bf35c0b38137')
}

db.tasks.insertOne({task_description:"create a file",task_status:"Success",task_timestamp:new Date()})
{
  acknowledged: true,
  insertedId: ObjectId('6836e0b31f69bf35c0b38139')
}

db.tasks.insertOne({task_description:"save file",task_status:"pending",task_timestamp:new Date()})
{
  acknowledged: true,
  insertedId: ObjectId('6836e0c51f69bf35c0b3813a')
}

db.tasks.insertOne({task_description:"task done",task_status:false,task_timestamp:new Date()})
{
  acknowledged: true,
  insertedId: ObjectId('6836e72d1f69bf35c0b3813b')
}

db.tasks.find()
{
  _id: ObjectId('6836e08a1f69bf35c0b38138'),
  task_description: 'create a file',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:10.689Z
}

{
  _id: ObjectId('6836e0b31f69bf35c0b38139'),
  task_description: 'Write content',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:51.032Z
}

{
  _id: ObjectId('6836e0c51f69bf35c0b3813a'),
  task_description: 'save file',
  task_status: false,
  task_timestamp: 2025-05-28T10:09:09.471Z
}

{
  _id: ObjectId('6836e72d1f69bf35c0b3813b'),
  task_description: 'task done',
  task_status: false,
  task_timestamp: 2025-05-28T10:36:29.547Z
}

db.tasks.updateMany({},{$set:{createdAt:new Date(),updatedAt:new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 6,
  modifiedCount: 6,
  upsertedCount: 0
}

db.tasks.find()
{
  _id: ObjectId('6836e08a1f69bf35c0b38138'),
  task_description: 'create a file',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:10.689Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e0b31f69bf35c0b38139'),
  task_description: 'Write content',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:51.032Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e0c51f69bf35c0b3813a'),
  task_description: 'save file',
  task_status: false,
  task_timestamp: 2025-05-28T10:09:09.471Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}
{
  _id: ObjectId('6836e72d1f69bf35c0b3813b'),
  task_description: 'task done',
  task_status: false,
  task_timestamp: 2025-05-28T10:36:29.547Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

db.tasks.updateOne({task_description:"task done"},{$set:{task_status:true,updatedAt:new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

db.tasks.find({task_description:"task done"})
{
  _id: ObjectId('6836e72d1f69bf35c0b3813b'),
  task_description: 'task done',
  task_status: true,
  task_timestamp: 2025-05-28T10:36:29.547Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T11:09:03.290Z
}

db.tasks.countDocuments()
5


db.tasks.find().sort()
{
  _id: ObjectId('6836dff71f69bf35c0b38137'),
  task_status: true,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e08a1f69bf35c0b38138'),
  task_description: 'create a file',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:10.689Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e0b31f69bf35c0b38139'),
  task_description: 'Write content',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:51.032Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e0c51f69bf35c0b3813a'),
  task_description: 'save file',
  task_status: false,
  task_timestamp: 2025-05-28T10:09:09.471Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e72d1f69bf35c0b3813b'),
  task_description: 'task done',
  task_status: true,
  task_timestamp: 2025-05-28T10:36:29.547Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T11:09:03.290Z
}


db.tasks.updateMany({},{$set:{Duedate:new Date()}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 5,
  modifiedCount: 5,
  upsertedCount: 0
}

db.tasks.find({task_description:"save file"})
{
  _id: ObjectId('6836e0c51f69bf35c0b3813a'),
  task_description: 'save file',
  task_status: false,
  task_timestamp: 2025-05-28T10:09:09.471Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z,
  Duedate: 2025-05-28T11:21:58.862Z
}



db.tasks.find({
  createdAt: {
    $gte: new Date(Date.now() - 20 * 60 * 1000)
  }
})
{
  _id: ObjectId('6836dff71f69bf35c0b38137'),
  task_status: true,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e08a1f69bf35c0b38138'),
  task_description: 'create a file',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:10.689Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e0b31f69bf35c0b38139'),
  task_description: 'Write content',
  task_status: true,
  task_timestamp: 2025-05-28T10:08:51.032Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e0c51f69bf35c0b3813a'),
  task_description: 'save file',
  task_status: false,
  task_timestamp: 2025-05-28T10:09:09.471Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T10:50:50.033Z
}

{
  _id: ObjectId('6836e72d1f69bf35c0b3813b'),
  task_description: 'task done',
  task_status: true,
  task_timestamp: 2025-05-28T10:36:29.547Z,
  createdAt: 2025-05-28T10:50:50.033Z,
  updatedAt: 2025-05-28T11:09:03.290Z
}
