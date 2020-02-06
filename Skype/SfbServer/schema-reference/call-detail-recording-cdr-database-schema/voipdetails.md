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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: VoIPDetails ビューには、ピアツーピアセッションに関する情報が格納されます。これは、少なくとも1人のユーザーが VoIP ユーザーである場合です。 このビューは、Microsoft Lync Server 2013 で導入されました。
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814775"
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
   

