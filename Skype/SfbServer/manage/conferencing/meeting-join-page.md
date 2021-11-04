---
title: '[会議への参加] ページを [会議] で構成Skype for Business Server'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: 会議の参加ページを構成する方法については、Skype for Business Server。'
ms.openlocfilehash: 39a9fd42fd7d1017ece572856f6d85a09e1f55fe
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743563"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>[会議への参加] ページを [会議] で構成Skype for Business Server
 
**概要:** 会議参加ページを構成する方法については、Skype for Business Server。
  
ユーザーが会議出席依頼の会議リンクをクリックすると、会議参加ページは、Skype for Business クライアントが既にユーザーのコンピューターにインストールされているかどうかを検出します。 クライアントがすでにインストールされている場合、クライアントがミーティングを開き、参加します。 クライアントがインストールされていない場合は、既定でクライアントSkype for Business開きます。 
  
## <a name="configure-the-meeting-join-page"></a>会議参加ページの構成

ユーザーが他のバージョンのクライアントとの会議に参加できる場合は、会議参加ページの動作を変更できます。 これらの構成オプションは、Skype for Business Serverコントロール パネルから削除されましたが、Set-CsWebServiceConfigurationコマンドレットを使用して構成します。
  
**会議参加ページのSet-CsWebServiceConfigurationパラメーター**

|**Set-CsWebServiceConfiguration パラメーター**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |このパラメーターは、オンプレミスバージョンのサーバーで使用Skype for Business Server。  <br/> True に設定すると、Skype for Business 以外のクライアント アプリケーションを使用して会議に参加するユーザーには、現在のクライアント アプリケーションを使用して会議に参加する機会が与えられる。 既定値は False です。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |このパラメーターは、オンプレミスバージョンのサーバーで使用Skype for Business Server。  <br/>  True に設定すると、オンライン会議に参加するための代替オプションが自動的に展開され、ユーザーに表示されます。 False (既定値) に設定すると、これらのオプションを使用できますが、ユーザーはオプションの一覧を表示する必要があります。  <br/> |
   

