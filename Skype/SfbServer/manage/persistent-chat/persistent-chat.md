---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法を説明します。'
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの管理
 
**の概要:**ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法について説明します。
  
組織の永続的なチャット サーバーを設定すると、初期展開時に構成を指定します。 ただし、永続的なチャット サーバーのサポートを実装する方法を変更する場合があります。 などの永続的なチャット サーバーのサポートと、特定のチームまたは組織内のグループに異なるコントロールを設定する必要があります。 このセクションでは、情報と、永続的なチャット サーバーの展開をカスタマイズするための手順を提供します。 永続的なチャット サーバーの構成可能な機能に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。 永続的なチャット サーバーの展開に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なのチャット サーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。 
  
コントロール パネルを使用するか、Windows PowerShell コマンドレットを使用して、永続的なチャット サーバーを管理できます。 
  
コントロール パネルを使用するには
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. **[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。
    
3. 左側のナビゲーション ・ バーでは、**永続的なチャット**をクリックします。
    
次の表は、永続的なチャット サーバーを管理するために利用可能な Windows PowerShell コマンドレットをまとめたものです。 などのすべての利用可能なパラメーターの構文の詳細については、 [Skype ビジネス サーバー 2015 管理シェルに](../management-shell.md)を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|新しい-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|セット CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得する  <br/> |
|削除 CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
|新しい-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|セット CsPersistentChatRoom  <br/> |既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる  <br/> |
|Get CsPersistentChatRoom  <br/> |ルームについての情報を取得します。  <br/> |
|クリア CsPersistentChatRoom  <br/> |ルームをクリアするか、またはルームからメッセージをクリアする  <br/> |
|削除 CsPersistentChatRoom  <br/> |ルームを削除する  <br/> |
|削除 CsPersistentChatMessage  <br/> |ルームからメッセージを削除する  <br/> |
|新しい-CsPersistentChatAddin  <br/> |新しいアドインを作成する  <br/> |
|セット CsPersistentChatAddin  <br/> |既存のアドインの設定を構成する  <br/> |
|Get CsPersistentChatAddin  <br/> |アドインに関する情報を取得する  <br/> |
|削除 CsPersistentChatAddin  <br/> |アドインを削除する  <br/> |
|セット CsPersistentChatComplianceConfiguration  <br/> |コンプライアンス構成設定の既存のコレクションを変更する  <br/> |
|エクスポート CsPersistentChatData  <br/> |常設チャット データベースからデータをエクスポートする  <br/> |
|インポート-CsPersistentChatData  <br/> |以前のバージョンの Lync Server からエクスポートされたデータをインポートする  <br/> |
   

