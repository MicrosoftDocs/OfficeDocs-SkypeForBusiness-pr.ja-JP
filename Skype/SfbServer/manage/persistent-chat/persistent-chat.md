---
title: 2015 年の常設チャット サーバー Skype for Business Serverする
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: 2015 年に常設チャット サーバーを管理するSkype for Business Serverします。'
ms.openlocfilehash: 821442de529c50d8ac8db3ab5272dcc48d06c8e5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766475"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>2015 年の常設チャット サーバー Skype for Business Serverする
 
**概要:** 2015 年に常設チャット サーバーを管理するSkype for Business Serverします。
  
組織の常設チャット サーバーをセットアップする場合は、展開時に初期構成を指定します。 ただし、常設チャット サーバーのサポートの実装方法を変更する場合があります。 たとえば、組織内の特定のチームまたはグループに対して常設チャット サーバーのサポートとコントロールを異なる方法で設定する必要がある場合があります。 このセクションでは、常設チャット サーバーの展開をカスタマイズするための情報と手順について説明します。 常設チャット サーバー用に構成できる機能の詳細については、「Plan [for Persistent Chat Server in Skype for Business Server 2015」を参照](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)してください。 常設チャット サーバーの展開の詳細については、「Deploy Persistent Chat Server in Skype for Business Server [2015」を参照](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)してください。 

> [!NOTE]
> 常設チャットは 2015 Skype for Business Serverで使用できますが、2019 年Skype for Business Serverではサポートされていません。 同じ機能は、Teams。 詳細については、「アップグレードの開始[方法」をMicrosoft Teamsしてください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、2015 年Skype for Business Serverします。 
  
常設チャット サーバーは、コントロール パネルを使用するか、またはコマンドレットを使用Windows PowerShellできます。 
  
コントロール パネルを使用するには、次の操作を行います。
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート **] メニュー** から、[コントロール パネル] Skype for Business Serverを選択するか、ブラウザー ウィンドウを開き、[管理 URL] を入力します。
    
3. 左側のナビゲーション バーで、[常設チャット] **をクリックします**。
    
次の表に、常設チャット サーバー Windows PowerShellに使用できるコマンドレットの概要を示します。 使用可能なすべてのパラメーターを含む構文の詳細については[、「Skype for Business Server 2015 管理シェル」を参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得します  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成します。ユーザーとユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |会議室に関する情報を取得します。  <br/> |
|Clear-CsPersistentChatRoom  <br/> |ルームまたはルームからのメッセージをクリアする  <br/> |
|Remove-CsPersistentChatRoom  <br/> |ルームを削除する  <br/> |
|Remove-CsPersistentChatMessage  <br/> |ルームからメッセージを削除する  <br/> |
|New-CsPersistentChatAddin  <br/> |新しいアドインを作成する  <br/> |
|Set-CsPersistentChatAddin  <br/> |既存のアドインの設定を構成する  <br/> |
|Get-CsPersistentChatAddin  <br/> |アドインに関する情報を取得します。  <br/> |
|Remove-CsPersistentChatAddin  <br/> |アドインを削除する  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |コンプライアンス構成設定の既存のコレクションを変更します。  <br/> |
|Export-CsPersistentChatData  <br/> |常設チャット データベースからデータをエクスポートする  <br/> |
|Import-CsPersistentChatData  <br/> |以前のバージョンの Lync Server からエクスポートされたデータをインポートする  <br/> |
   

