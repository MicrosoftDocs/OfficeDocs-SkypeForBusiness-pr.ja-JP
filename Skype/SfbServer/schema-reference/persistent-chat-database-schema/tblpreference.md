---
title: tblPreference
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
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアント設定が含まれる。 これは通常、Lync 2013 より前のクライアントで使用されます。
ms.openlocfilehash: e9b4518fbe203750406fe02a3a69b04d1e45a9c1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578601"
---
# <a name="tblpreference"></a>tblPreference

tblPreference には、ユーザーのクライアント設定が含まれる。 これは通常、Lync 2013 より前のクライアントで使用されます。

**列**


| **列**            | **型**                        | **説明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | NULL でない nvarchar (255)  <br/> | 次のような形式のラベル \<user sip uri\>                   |
| prefSeqID  <br/>      | NULL でない int  <br/>            | バージョン管理を行う目的で、連続する番号 (ラベルごとに) を指定します。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | エンコードされたコンテンツ。  <br/>                                         |
| lastModifiedBy  <br/> | NULL でない int  <br/>            | 基本設定を更新したプリンシパルの ID。  <br/>         |

**Key**

|**列**|**説明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主キー。  <br/> |


