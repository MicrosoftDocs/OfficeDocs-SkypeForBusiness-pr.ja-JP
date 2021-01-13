---
title: tblConfig
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、一部の常設チャット サーバーでサポートされていない構成が 1 行に含まれている。
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809737"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、一部の常設チャット サーバーでサポートされていない構成が 1 行に含まれている。
  
**Columns**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |NULL でない nvarchar (255)  <br/> |"プール" を含みます。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |構成の内容です。  <br/> |
|configPoolID  <br/> |NULL でない GUID  <br/> |データベース インスタンスの一意の識別子。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |主キー。  <br/> |
   

