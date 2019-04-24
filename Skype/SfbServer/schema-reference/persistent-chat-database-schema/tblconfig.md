---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213068"
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
   

