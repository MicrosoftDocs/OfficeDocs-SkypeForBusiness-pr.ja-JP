---
title: VoIPDetails ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 5804f32dfebb2fe8c6844acb0bcd343c5b6ead21
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385405"
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
   

