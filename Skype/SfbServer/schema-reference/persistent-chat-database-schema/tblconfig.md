---
title: tblConfig
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
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig には、いくつか永続的なチャット サーバー サポートされていない構成、1 つの行が含まれています。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255)、null でないです。  <br/> |。「プール」が含まれています  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |設定内容です。  <br/> |
|configPoolID  <br/> |GUID では、null でないです。  <br/> |データベース ・ インスタンスの一意の ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|configLabel  <br/> |プライマリ ・ キーです。  <br/> |
   

