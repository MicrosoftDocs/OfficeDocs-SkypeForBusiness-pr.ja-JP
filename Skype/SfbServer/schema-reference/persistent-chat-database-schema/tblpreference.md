---
title: tblPreference
ms.reviewer: ''
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
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212538"
---
# <a name="tblpreference"></a>tblPreference

tblPreference には、ユーザーのクライアントの設定が含まれています。 これは一般に、Lync 2013 の前にあるクライアントが使用されます。

**列**


| **列**            | **型**                        | **説明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255)、null でないです。  <br/> | 形式で次のようにラベルを付ける:\<ユーザーの sip uri\>                   |
| prefSeqID  <br/>      | int 型、null でないです。  <br/>            | バージョン管理の目的 (ラベル) あたりの連番です。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | エンコードされたコンテンツです。  <br/>                                         |
| lastModifiedBy  <br/> | int 型、null でないです。  <br/>            | プリファレンスを更新するプリンシパルの ID です。  <br/>         |

**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prefLabel、prefSeqID\>  <br/> |プライマリ ・ キーです。  <br/> |


