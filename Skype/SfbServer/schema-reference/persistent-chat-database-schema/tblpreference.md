---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 8c719ba33196e32d48f045c07ea89ded317ab5ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846190"
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

**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主キー。  <br/> |


