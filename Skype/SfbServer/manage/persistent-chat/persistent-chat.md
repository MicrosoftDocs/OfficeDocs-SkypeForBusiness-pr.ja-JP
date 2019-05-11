---
title: Skype for Business Server 2015 での常設チャット サーバーの管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '概要: ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法を説明します。'
ms.openlocfilehash: 27405be6d209089c670aa117838e959bae64d9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910222"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での常設チャット サーバーの管理
 
**の概要:** ビジネス サーバー 2015 の Skype での永続的なチャット サーバーを管理する方法について説明します。
  
組織の永続的なチャット サーバーを設定すると、初期展開時に構成を指定します。 ただし、永続的なチャット サーバーのサポートを実装する方法を変更する場合があります。 などの永続的なチャット サーバーのサポートと、特定のチームまたは組織内のグループに異なるコントロールを設定する必要があります。 このセクションでは、情報と、永続的なチャット サーバーの展開をカスタマイズするための手順を提供します。 永続的なチャット サーバーの構成可能な機能に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)を参照してください。 永続的なチャット サーバーの展開に関する詳細については、[ビジネス サーバー 2015 の Skype での永続的なのチャット サーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。 

> [!NOTE]
> 永続的なチャットですがビジネス サーバー 2015 の Skype で利用可能なビジネス サーバー 2019 の Skype でサポートされていません。 同じ機能は、チームで使用できます。 詳細については、[マイクロソフトのチームにビジネス用の Skype からの旅](/microsoftteams/journey-skypeforbusiness-teams)を参照してください。 永続的なチャットを使用する場合は、選択肢は、いずれかをチームでは、この機能を必要とするユーザーを移行するまたはビジネス サーバー 2015 の Skype を使用し続ける。 
  
コントロール パネルを使用するか、Windows PowerShell コマンドレットを使用して、永続的なチャット サーバーを管理できます。 
  
コントロール パネルを使用するには
  
1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. **[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。
    
3. 左側のナビゲーション ・ バーでは、**永続的なチャット**をクリックします。
    
次の表は、永続的なチャット サーバーを管理するために利用可能な Windows PowerShell コマンドレットをまとめたものです。 使用できるすべてのパラメーターを含む構文の詳細については、「[Skype for Business Server 2015 Management Shell](../management-shell.md)」を参照してください。
  

|**コマンドレット**|**説明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |新しいカテゴリを作成する  <br/> |
|Set-CsPersistentChatCategory  <br/> |既存のカテゴリの設定を構成する  <br/> |
|Get-CsPersistentChatCategory  <br/> |カテゴリに関する情報を取得する  <br/> |
|Remove-CsPersistentChatCategory  <br/> |カテゴリを削除する  <br/> |
|New-CsPersistentChatRoom  <br/> |新しいチャット ルームを作成する  <br/> |
|Set-CsPersistentChatRoom  <br/> |既存のルームの設定を構成し、ユーザーおよびユーザー グループをルームに割り当てる  <br/> |
|Get-CsPersistentChatRoom  <br/> |ルームについての情報を取得します。  <br/> |
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
   

