---
title: VoIPDetails ビュー
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューでは、ピア ツー ピア セッションでは、少なくとも 1 つは VoIP ユーザーに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212706"
---
# <a name="voipdetails-view"></a>VoIPDetails ビュー
 
VoIPDetails ビューでは、ピア ツー ピア セッションでは、少なくとも 1 つは VoIP ユーザーに関する情報を格納します。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> VoIPDetails ビューが含まれていますすべて[SessionDetails ビュー](sessiondetails-0.md)内の列のさらに以下の列には。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |電話セッションを開始したユーザーの URI です。  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |電話のセッションに参加したユーザーの URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |セッションを切断したユーザーの URI。  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |セッションを切断したユーザーの URI の種類です。 詳細については、 [UriTypes テーブル](uritypes.md)を参照してください。 <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |セッションを切断したユーザーのテナントです。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |電話セッションを切断したユーザーの URI です。  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |仲介サーバーがセッションを開始したユーザーが使用します。  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |仲介サーバーがセッションに参加したユーザーが使用します。  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |ゲートウェイは、セッションを開始したユーザーが使用します。  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |セッションに参加しているユーザーによって使用されるゲートウェイです。  <br/> |
   

