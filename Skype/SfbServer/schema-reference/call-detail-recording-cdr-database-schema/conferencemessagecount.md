---
title: Skype for Business Server 2015 の ConferenceMessageCount テーブル
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
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: この表の各レコードは、1 つの IM 会議で 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含む。 各電話会議は、この表の複数のレコードで表されます。ユーザーごとに 1 つのレコード。
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813277"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の ConferenceMessageCount テーブル
 
この表の各レコードは、1 つの IM 会議で 1 人のユーザーを表し、そのユーザーが送信したメッセージの数を含む。 各電話会議は、この表の複数のレコードで表されます。ユーザーごとに 1 つのレコード。
  
|**列**|**データ型**|**キー/インデックス**|**詳細**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |日付型  <br/> |主/プライマリ、外部  <br/> |会議インスタンスの時間。 **SessionIdSeq と組み合わせて使用して**、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主/プライマリ、外部  <br/> |会議インスタンスを識別する ID 番号。 **SessionIdTime と組み合わせて使用し**、会議インスタンスを一意に識別します。 詳細については [、Skype for Business Server 2015](conferences.md) の電話会議の表を参照してください。 <br/> |
|**UserId** <br/> |int  <br/> |外部  <br/> |Users テーブルから参照される、このユーザーを識別する一[意の番号。](users.md)  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |このユーザーが会議中に送信したメッセージの数。  <br/> |
   

