---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: Skype for Business Server 2015 で常設チャット サーバーを管理する方法について学習します。'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832887"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの管理
 
**概要:** Skype for Business Server 2015 で常設チャット サーバーを管理する方法について学習します。
  
組織の常設チャット サーバーをセットアップするときに、展開時に初期構成を指定します。 ただし、常設チャット サーバーのサポートの実装方法を変更する必要がある場合があります。 たとえば、組織内の特定のチームまたはグループに対して、常設チャット サーバーのサポートと制御を異なる方法で設定する必要がある場合があります。 このセクションでは、常設チャット サーバーの展開をカスタマイズするための情報と手順について説明します。 常設チャット サーバー用に構成できる機能の詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015」](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。 常設チャット サーバーの展開の詳細については [、「Deploy Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。 

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
  
常設チャット サーバーは、コントロール パネルを使用するか、または次のコマンドレットをWindows PowerShellできます。 
  
コントロール パネルを使用するには:
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。
    
3. 左側のナビゲーション バーで、[常設チャット] **をクリックします**。
    
次の表に、常設チャット Windows PowerShell管理に使用できるすべてのコマンドレットの概要を示します。 使用可能なすべてのパラメーターを含む構文の詳細については [、Skype for Business Server 2015 管理シェルを参照してください](../management-shell.md)。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成します。  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成します  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得します  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除します  <br/> |
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成します  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成します。ユーザーとユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |ルームに関する情報を取得します  <br/> |
|Clear-CsPersistentChatRoom  <br/> |ルームまたはメッセージをルームからクリアします  <br/> |
|Remove-CsPersistentChatRoom  <br/> |ルームを削除します  <br/> |
|Remove-CsPersistentChatMessage  <br/> |ルームからメッセージを削除します  <br/> |
|New-CsPersistentChatAddin  <br/> |新しいアドインを作成します。  <br/> |
|Set-CsPersistentChatAddin  <br/> |既存のアドインの設定を構成します。  <br/> |
|Get-CsPersistentChatAddin  <br/> |アドインに関する情報を取得します  <br/> |
|Remove-CsPersistentChatAddin  <br/> |アドインを削除します  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |コンプライアンス構成設定の既存のコレクションを変更します  <br/> |
|Export-CsPersistentChatData  <br/> |常設チャット データベースからデータをエクスポートします。  <br/> |
|Import-CsPersistentChatData  <br/> |以前のバージョンの Lync Server からエクスポートされたデータをインポートします。  <br/> |
   

