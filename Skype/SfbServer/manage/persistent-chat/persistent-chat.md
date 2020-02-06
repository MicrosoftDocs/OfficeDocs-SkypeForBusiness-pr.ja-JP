---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: Skype for Business Server 2015 で常設チャットサーバーを管理する方法について説明します。'
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817323"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの管理
 
**概要:** Skype for Business Server 2015 で常設チャットサーバーを管理する方法について説明します。
  
組織に常設チャットサーバーを設定する場合は、展開時に初期構成を指定します。 ただし、常設チャットサーバーサポートの実装方法を変更する必要がある場合もあります。 たとえば、組織内の特定のチームまたはグループに対して、常設チャットサーバーのサポートとコントロールを設定する必要がある場合があります。 このセクションには、常設チャットサーバーの展開をカスタマイズするための情報と手順が記載されています。 常設チャットサーバー用に構成できる機能の詳細については、「 [Skype For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」を参照してください。 常設チャットサーバーの展開について詳しくは、「 [Skype For Business server 2015 での常設チャットサーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)」をご覧ください。 

> [!NOTE]
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。 常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。 
  
常設チャットサーバーを管理するには、コントロールパネルを使用するか、Windows PowerShell コマンドレットを使用します。 
  
コントロール パネルを使用するには
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. [**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。
    
3. 左側のナビゲーションバーで、[**常設チャット**] をクリックします。
    
次の表は、常設チャットサーバーを管理するために使用できる Windows PowerShell コマンドレットをまとめたものです。 使用できるすべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得する  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |会議室に関する情報を取得します  <br/> |
|Clear-CsPersistentChatRoom  <br/> |ルームをクリアするか、またはルームからメッセージをクリアする  <br/> |
|Remove-CsPersistentChatRoom  <br/> |ルームを削除する  <br/> |
|Remove-CsPersistentChatMessage  <br/> |ルームからメッセージを削除する  <br/> |
|New-CsPersistentChatAddin  <br/> |新しいアドインを作成する  <br/> |
|Set-CsPersistentChatAddin  <br/> |既存のアドインの設定を構成する  <br/> |
|Get-CsPersistentChatAddin  <br/> |アドインに関する情報を取得する  <br/> |
|Remove-CsPersistentChatAddin  <br/> |アドインを削除する  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |コンプライアンス構成設定の既存のコレクションを変更する  <br/> |
|Export-CsPersistentChatData  <br/> |常設チャット データベースからデータをエクスポートする  <br/> |
|Import-CsPersistentChatData  <br/> |以前のバージョンの Lync Server からエクスポートされたデータをインポートする  <br/> |
   

