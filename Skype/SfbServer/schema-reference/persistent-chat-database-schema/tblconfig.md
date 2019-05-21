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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295455"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、一部の常設チャットサーバーでサポートされない構成が1つの行に含まれています。
  
**行**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)、null ではない  <br/> |[プール] が含まれています。  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |構成コンテンツ。  <br/> |
|configPoolID  <br/> |GUID、null ではない  <br/> |データベースインスタンスの一意の ID。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |主キー。  <br/> |
   

