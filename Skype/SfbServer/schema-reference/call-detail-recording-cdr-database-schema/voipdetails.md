---
title: VoIPDetails ビュー
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 8e647f79953efc507e63aa4f19e6f1deba53d7a1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765085"
---
# <a name="voipdetails-view"></a>VoIPDetails ビュー
 
VoIPDetails ビューには、少なくとも 1 人のユーザーが VoIP ユーザーであるピアツーピア セッションに関する情報が格納されます。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> VoIPDetails ビューには、以下に示す列に加えて [、SessionDetails](sessiondetails-0.md) ビューのすべての列が含まれます。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |セッションを開始したユーザーの 電話 URI。  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |セッションに参加したユーザーの 電話 URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |セッションを切断したユーザーの URI。  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |セッションを切断したユーザーの URI の種類。 詳細については [、UriTypes テーブル](uritypes.md) を参照してください。 <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |セッションを切断したユーザーのテナント。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |セッションを切断したユーザーの 電話 URI。  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーの仲介サーバー。  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーの仲介サーバー。  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーが使用するゲートウェイ。  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用するゲートウェイ。  <br/> |
   

