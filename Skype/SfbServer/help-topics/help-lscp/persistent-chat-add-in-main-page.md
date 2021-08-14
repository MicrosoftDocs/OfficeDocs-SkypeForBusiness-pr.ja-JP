---
title: 常設チャット アドイン メイン ページ
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
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: '[常設チャット] ページの [アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、会話機能拡張ウィンドウのチャット ルームのクライアントに表示されます。 管理者は、登録されたアドインのリストにアドインを追加する必要があります。また、チャット ルームの管理者/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録されたアドインの 1 つとルームを関連付ける必要があります。'
ms.openlocfilehash: c6f29cd9c9bf2b70b88a3ca3e5e1ac230b56e2a111cc34cc405261d3947e003b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343691"
---
# <a name="persistent-chat-add-in-main-page"></a>常設チャット アドイン メイン ページ

[常設チャット]**ページの**[アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、会話機能拡張ウィンドウのチャット ルームのクライアントに表示されます。 管理者は、登録されたアドインのリストにアドインを追加する必要があります。また、チャット ルームの管理者/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録されたアドインの 1 つとルームを関連付ける必要があります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインには、株式ティッカーがチャット ルームに投稿され、拡張ウィンドウに在庫履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。 また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。

常設チャット ルーム用のアドインを作成するには[、「Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015」を参照](../../manage/persistent-chat/configure-add-ins.md)してください。 常設チャット管理者の場合は、コントロール パネルまたはコマンドレットを使用してアドインWindows PowerShellできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**アドイン**] ページでは、次のタスクを実行できます。

- [2015 年に常設チャット ルーム用のアドインをSkype for Business Serverする](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. [スタート **] メニュー** から、[コントロール パネル] Skype for Business Serverを選択するか、ブラウザー ウィンドウを開き、[管理 URL] を入力します。 コントロール パネルの起動に使用できるさまざまな方法の詳細については [、「Open Lync Server 管理ツール」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。

3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。

    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。

4. [**アドイン**] ページで、[**新規**] をクリックします。

5. [ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 アドインをプール間で移動したり、複数のプールで共有したりすることはできません。

6. [**新規 アドイン**] で、次の操作を実行します。

   - [**名前**] に、新しいアドインの名前を指定します。

   - [**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。

7. [**確定**] をクリックします。

## <a name="see-also"></a>関連項目

常設チャット サーバーの機能の詳細については、「Plan for Persistent Chat [Server in Skype for Business Server 2015」、2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)年 Skype for Business Server 年の常設チャット サーバーの展開、および Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)年の常設チャット サーバー[の](../../manage/persistent-chat/persistent-chat.md)管理を参照してください。