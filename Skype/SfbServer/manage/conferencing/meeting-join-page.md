---
title: 会議を構成するビジネス サーバー 2015 の Skype での参加のページ
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '概要: 会議を構成する方法を学習する Skype のビジネス サーバー 2015 のページを結合します。'
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a>会議を構成するビジネス サーバー 2015 の Skype での参加のページ
 
**の概要:**会議を構成する方法については Skype のビジネス サーバー 2015 のページを結合します。
  
ユーザーが会議出席依頼、会議の会議のリンクをクリックすると結合のページは、ユーザーのコンピューターで、Skype のビジネスのクライアントが既にインストールされているかどうかを検出します。 クライアントが既にインストールされている場合、クライアントが開き、ミーティングに参加します。 クライアントがインストールされていない場合既定では、2015年バージョン Skype のビジネス クライアントが開きます。 
  
## <a name="configure-the-meeting-join-page"></a>会議を構成する結合のページ

会議の結合の動作を変更するページの他のバージョンのクライアントとの会議に参加するユーザーを許可する場合。 これらの構成オプションは、ビジネス サーバーのコントロール パネルの Skype から削除されていますが、セット CsWebServiceConfiguration コマンドレットを使用して、それらを構成します。
  
**ミーティング参加ページ セットの CsWebServiceConfiguration のパラメーター**

|**パラメーターのセット CsWebServiceConfiguration**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |ビジネス サーバー 2015 の Skype の設置型バージョンで使用するため、このパラメーターは廃止されました。  <br/> かどうか True に設定する、以外のクライアント アプリケーションを使用してミーティングに参加するユーザー ビジネス用の Skype は機会がある、現在のクライアント アプリケーションを使用してミーティングに参加します。 既定値は False です。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |ビジネス サーバー 2015 の Skype の設置型バージョンで使用するため、このパラメーターは廃止されました。  <br/>  かどうかは True に設定すると、代替オプションのオンライン会議に参加するため自動的に展開され、ユーザーに表示します。 場合は False (既定値) に設定すると、これらのオプションを使用できるがユーザー自身でオプションの一覧を表示します。  <br/> |
   

