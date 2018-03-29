---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアントの設定が含まれています。 これは一般に、Lync 2013 の前にあるクライアントが使用されます。
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a>tblPreference
 
tblPreference には、ユーザーのクライアントの設定が含まれています。 これは一般に、Lync 2013 の前にあるクライアントが使用されます。
  
**列**

|**列**|**タイプ**|**説明**|
|:-----|:-----|:-----|
|prefLabel  <br/> |nvarchar (255)、null でないです。  <br/> |形式で次のようにラベルを付ける:\<ユーザーの sip uri\>|ユーザー名です。\<セットの優先順位\>。  <br/> |
|prefSeqID  <br/> |int 型、null でないです。  <br/> |バージョン管理の目的 (ラベル) あたりの連番です。  <br/> |
|prefContent  <br/> |nvarchar (max)  <br/> |エンコードされたコンテンツです。  <br/> |
|lastModifiedBy  <br/> |int 型、null でないです。  <br/> |プリファレンスを更新するプリンシパルの ID です。  <br/> |
   
**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prefLabel、prefSeqID\>  <br/> |プライマリ ・ キーです。  <br/> |
   

