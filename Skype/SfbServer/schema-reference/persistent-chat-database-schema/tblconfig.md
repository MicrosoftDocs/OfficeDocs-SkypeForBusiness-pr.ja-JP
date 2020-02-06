---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814625"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。
  
**行**

|**列**|**種類**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)、null ではない  <br/> |[プール] が含まれています。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |構成コンテンツ。  <br/> |
|configPoolID  <br/> |GUID、null ではない  <br/> |データベースインスタンスの一意の ID。  <br/> |
   
**Key**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |主キー。  <br/> |
   

