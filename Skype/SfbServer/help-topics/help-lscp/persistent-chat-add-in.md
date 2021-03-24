---
title: 常設チャット アドイン
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: '[常設チャット] ページの [アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、会話機能拡張ウィンドウのチャット ルームのクライアントに表示されます。 管理者は、登録されたアドインのリストにアドインを追加する必要があります。また、チャット ルームの管理者/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録されたアドインの 1 つとルームを関連付ける必要があります。'
ms.openlocfilehash: c90383a26c658e8da73df09368a5d8fe04cfe69b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099503"
---
# <a name="persistent-chat-add-in"></a>常設チャット アドイン

[常設チャット]**ページの**[アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、会話機能拡張ウィンドウのチャット ルームのクライアントに表示されます。 管理者は、登録されたアドインのリストにアドインを追加する必要があります。また、チャット ルームの管理者/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録されたアドインの 1 つとルームを関連付ける必要があります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインには、株式ティッカーがチャット ルームに投稿され、拡張ウィンドウに在庫履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。 また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。

常設チャット ルーム用のアドインを作成するには [、「Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015」を参照](../../manage/persistent-chat/configure-add-ins.md)してください。 常設チャット管理者の場合は、コントロール パネルまたはコマンドレットを使用してアドインWindows PowerShellできます。

## <a name="tasks-that-you-can-perform"></a>実行できるタスク

[**アドイン**] ページでは、次のタスクを実行できます。

- [Skype for Business Server 2015 で常設チャット ルームのアドインを構成する](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. [スタート **] メニュー** から、Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開き、管理 URL を入力します。 コントロール パネルの起動に使用できるさまざまな方法の詳細については [、「Open Lync Server 管理ツール」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。

3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。

    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。

4. [**アドイン**] ページで、[**新規**] をクリックします。

5. [ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 アドインをプール間で移動したり、複数のプールで共有したりすることはできません。

6. [**新規 アドイン**] で、次の操作を実行します。

   - [**名前**] に、新しいアドインの名前を指定します。

   - [**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。

7. [**確定**] をクリックします。

## <a name="see-also"></a>関連項目

常設チャット サーバーの機能の詳細については、「Plan for Persistent Chat Server in [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、Skype for Business Server 2015 での常設チャット サーバーの展開、および Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)での常設チャット サーバーの管理を参照してください。 [](../../manage/persistent-chat/persistent-chat.md)