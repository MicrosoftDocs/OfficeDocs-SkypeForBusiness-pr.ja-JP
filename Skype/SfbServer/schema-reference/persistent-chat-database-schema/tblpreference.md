---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアントの設定が含まれています。 これは一般に、Lync 2013 の前にあるクライアントが使用されます。
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929920"
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


