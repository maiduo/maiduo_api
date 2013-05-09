.. Maiduo HTTPAPI documentation master file, created by
   sphinx-quickstart on Thu May  9 13:30:11 2013.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Maiduo HTTPAPI's documentation!
==========================================

.. http:post:: /api/aps/device/

   注册设备，在didRegisterForRemoteNotificationsWithDeviceToken中注册Token
   如果Token更改或者第一次启动应用。

   **输出**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Content-Type: application/json

      {
        "pk": 1,
         "model": "ios_notifications.device",
         "fields": {
           "deactivated_at": null,
           "users": [],
           "service": 1,
           "platform": "",
           "last_notified_at": null,
           "is_active": true,
           "added_at": "2013-05-09T07:17:39Z",
           "os_version": "",
           "token": "a4faf00f4654246b9fd7e78ae29a49b321673892ae81721b8e74ad9d285b3c27",
           "display": ""
         }
       }

   :form service: 服务的ID，通常是1。
   :form token: iOS设备的Token。
   :statuscode: 201

.. http:post:: /api/aps/push/

   推送通知到iOS设备

  :form tokens: 设备Token - 逗号分隔多个Token，token1,token2。
  :form message: 推送消息内容。
  :form badge: 推送的badge数量。
  :form sound: 推送的声音。
  :form service: 服务的ID，通常是1。
  :form extra: 自定义的推送的内容，JSON格式。
  :form persis: 持久化，数据库中保留该次推送。
  :form no-persist: 不持久化，数据库不保留该次推送。
  :statuscode 201: 发送成功


Contents:

.. toctree::
   :maxdepth: 2



Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

