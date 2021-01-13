---
title: Skype for Business Server で会議参加ページを構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: Skype for Business Server で会議参加ページを構成する方法について学習します。'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828037"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>Skype for Business Server で会議参加ページを構成する
 
**概要:** Skype for Business Server で会議参加ページを構成する方法について学習します。
  
ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページは、Skype for Business クライアントがユーザーのコンピューターに既にインストールされているかどうかを検出します。 クライアントがすでにインストールされている場合、クライアントがミーティングを開き、参加します。 クライアントがインストールされていない場合は、既定で Skype for Business クライアントが開きます。 
  
## <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

ユーザーが他のバージョンのクライアントとの会議に参加できる場合は、会議参加ページの動作を変更できます。 これらの構成オプションは Skype for Business Server コントロール パネルから削除されましたが、次のコマンドレットを使用して構成Set-CsWebServiceConfigurationします。
  
**会議参加ページのSet-CsWebServiceConfigurationパラメーター**

|**Set-CsWebServiceConfiguration パラメーター**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |このパラメーターは、Skype for Business Server のオンプレミス バージョンで使用するために廃止されました。  <br/> True に設定されている場合、Skype for Business 以外のクライアント アプリケーションを使用して会議に参加するユーザーには、現在のクライアント アプリケーションを使用して会議に参加する機会が与えられる。 既定値は False です。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |このパラメーターは、Skype for Business Server のオンプレミス バージョンで使用するために廃止されました。  <br/>  True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。 False (既定値) に設定すると、これらのオプションを使用できますが、ユーザーは自分でオプションの一覧を表示する必要があります。  <br/> |
   

