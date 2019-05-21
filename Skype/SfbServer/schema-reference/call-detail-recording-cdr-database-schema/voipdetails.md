---
title: VoIPDetails ビュー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295665"
---
# <a name="voipdetails-view"></a>VoIPDetails ビュー
 
VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。 このビューは、Microsoft Lync Server 2013 で導入されました。
  
> [!NOTE]
> VoIPDetails ビューには、次に示す列と共に、 [Sessiondetails ビュー](sessiondetails-0.md)のすべての列が含まれています。
  
|**列**|**データ型**|**詳細**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |セッションを開始したユーザーの電話の URI。  <br/> |
|**電話番号** <br/> |nvarchar (450)  <br/> |セッションに参加したユーザーの電話の URI。  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |セッションを切断したユーザーの URI。  <br/> |
|**Uritん** <br/> |nvarchar(256)  <br/> |セッションを切断したユーザーの URI の種類。 詳細については、 [UriTypes の表](uritypes.md)を参照してください。 <br/> |
|**テナント** <br/> |nvarchar(256)  <br/> |セッションを切断したユーザーのテナント。  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |セッションを切断したユーザーの電話の URI。  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーによって使用された仲介サーバー。  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用した仲介サーバー。  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |セッションを開始したユーザーによって使用されたゲートウェイ。  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |セッションに参加したユーザーが使用したゲートウェイ。  <br/> |
   

