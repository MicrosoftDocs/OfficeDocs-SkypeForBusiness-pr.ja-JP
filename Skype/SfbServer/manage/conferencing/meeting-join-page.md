---
title: Skype for Business Server で会議の参加ページを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: Skype for Business Server で会議の参加ページを構成する方法について説明します。'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818518"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Skype for Business Server で会議の参加ページを構成する
 
**概要:** Skype for Business Server で会議の参加ページを構成する方法について説明します。
  
ユーザーが会議出席依頼の会議リンクをクリックすると、[会議の参加] ページによって、ユーザーのコンピューターに Skype for Business クライアントが既にインストールされているかどうかが検出されます。 クライアントが既にインストールされている場合は、クライアントが開き、会議に参加します。 クライアントがインストールされていない場合、既定では、Skype for Business クライアントが開きます。 
  
## <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

ユーザーが他のバージョンのクライアントと会議に参加できるようにする場合は、[会議参加] ページの動作を変更することができます。 これらの構成オプションは、Skype for Business Server コントロールパネルから削除されていますが、CsWebServiceConfiguration コマンドレットを使用して設定します。
  
**会議の参加ページの設定-CsWebServiceConfiguration パラメーター**

|**CsWebServiceConfiguration パラメーター**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |このパラメーターは、Skype for Business Server のオンプレミスバージョンで使用するために廃止されました。  <br/> True に設定すると、Skype for Business 以外のクライアントアプリケーションを使用して会議に参加するユーザーには、現在のクライアントアプリケーションを使用して会議に参加する機会が与えられます。 既定値は False です。  <br/> |
|Showalternatejoinoptionている  <br/> |このパラメーターは、Skype for Business Server のオンプレミスバージョンで使用するために廃止されました。  <br/>  True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。 False (既定値) に設定した場合、これらのオプションは使用できますが、ユーザーは独自のオプションの一覧を表示する必要があります。  <br/> |
   

