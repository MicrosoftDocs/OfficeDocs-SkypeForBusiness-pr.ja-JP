---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference には、ユーザーのクライアントの設定が含まれます。 通常、これは Lync 2013 より前のクライアントで使用されます。
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295343"
---
# <a name="tblpreference"></a>tblPreference

tblPreference には、ユーザーのクライアントの設定が含まれます。 通常、これは Lync 2013 より前のクライアントで使用されます。

**行**


| **列**            | **型**                        | **説明**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255)、null ではない  <br/> | 次のような形式のラベル\<。ユーザー sip uri\>                   |
| prefSeqID  <br/>      | int (null ではない)  <br/>            | バージョン管理のための連続番号 (ラベルあたり)。  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | エンコードされたコンテンツ。  <br/>                                         |
| 最終方法  <br/> | int (null ではない)  <br/>            | 設定を更新したプリンシパルの ID です。  <br/>         |

**キー**

|**列**|**説明**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |主キー。  <br/> |


