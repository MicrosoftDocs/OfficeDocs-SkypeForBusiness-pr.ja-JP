---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930023"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。
  
**列**

|**列**|**型**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)、null でないです。  <br/> |。「プール」が含まれています  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |設定内容です。  <br/> |
|configPoolID  <br/> |GUID では、null でないです。  <br/> |データベース ・ インスタンスの一意の ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |プライマリ ・ キーです。  <br/> |
   

