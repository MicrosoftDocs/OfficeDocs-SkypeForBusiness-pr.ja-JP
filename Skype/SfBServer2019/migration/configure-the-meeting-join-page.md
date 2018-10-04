---
title: 会議を構成する結合のページ
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ユーザーが会議出席依頼、会議の会議のリンクをクリックすると結合のページは、どのクライアントがユーザーのコンピューターに既にインストールされているを検出します。 クライアントが既にインストールされている場合、そのクライアントは開き、ミーティングに参加します。 クライアントがインストールされていない場合は、既定で Web アプリケーションを開きます。
ms.openlocfilehash: f7c66b7e7171e9d7f0dc39f30a7e99059e53a0c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374063"
---
# <a name="configure-the-meeting-join-page"></a>会議を構成する結合のページ

ユーザーが会議出席依頼、会議の会議のリンクをクリックすると結合のページは、どのクライアントがユーザーのコンピューターに既にインストールされているを検出します。 クライアントが既にインストールされている場合、そのクライアントは開き、ミーティングに参加します。 クライアントがインストールされていない場合は、既定で Web アプリケーションを開きます。
  
会議の結合の動作を変更することができますページの会議に参加するユーザーを許可する場合。 これらの構成オプションは、[コントロール パネル] から削除されたが、CsWebServiceConfiguration コマンドレットを使用して、それらを構成します。
  
**ミーティング参加ページの CsWebServiceConfiguration のパラメーター**

|**CsWebServiceConfiguration パラメーター**|**説明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |かどうかに True を設定する以外は、Lync クライアント アプリケーションを使用してミーティングに参加するユーザーが与えられますミーティングに参加することです。 既定値は False です。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |True の場合、別のオプションのオンライン会議に参加するに自動的に展開されユーザーに表示されるのです。 False (既定値) に設定すると、これらのオプションを使用できるが、ユーザー自身でオプションの一覧を表示します。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>会議を構成するのにはビジネス サーバー 2019 管理シェルには、Skype を使用して結合ページ

1. ビジネス サーバー 2019 管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネス サーバー 2019 の Skype をマイクロソフト**をクリック**ビジネス サーバー管理シェルの Skype**です。
    
2. 次のコマンドレットを実行します。 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    このコマンドレットは、web サービスの構成設定を返します。
    
3. パラメーターに設定する場合は True または False で、好みに応じて次のコマンドを実行 (このコマンドレットのパラメーターの詳細については、 [Skype](../../SfbServer/manage/management-shell.md)ビジネス サーバー管理シェルのマニュアルを参照してください)。
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


