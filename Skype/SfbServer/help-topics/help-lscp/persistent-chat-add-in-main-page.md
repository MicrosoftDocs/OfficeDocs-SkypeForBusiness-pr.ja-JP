---
title: 常設チャット アドイン メイン ページ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: '[常設チャット] ページの [アドイン] セクションを使って、Url を常設チャットルームに関連付けることができます。 これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。 管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。'
ms.openlocfilehash: 0fe522b440a3f99973ecafa04a9ef7a7cbc3962a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699972"
---
# <a name="persistent-chat-add-in-main-page"></a>常設チャット アドイン メイン ページ

[**常設チャット**] ページの [**アドイン**] セクションを使って、url を常設チャットルームに関連付けることができます。 これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。 管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインには、株式のティッカーがチャットルームに投稿されたときに受信する Silverlight アプリケーションを指す URL が含まれている場合があります。また、拡張機能ウィンドウには、株式履歴が表示されます。 チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。

常設チャットルーム用のアドインを作成するには、「 [Skype For Business Server 2015 の常設チャットルーム用のアドインを設定](../../manage/persistent-chat/configure-add-ins.md)する」を参照してください。 常設チャットの管理者である場合は、コントロールパネルまたは Windows PowerShell コマンドレットを使用してアドインを作成できます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**アドイン**] ページでは、次のタスクを実行できます。

- [Skype for Business Server 2015 での常設チャット ルームのアドインの構成](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. [**スタート**] メニューで、[Skype For business Server] コントロールパネルを選択するか、ブラウザーウィンドウを開き、管理 URL を入力します。 コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)」を参照してください。

3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。

    複数の常設チャットサーバープールの展開の場合、ドロップダウンリストから適切なプールを選択します。

4. [**アドイン**] ページで、[**新規**] をクリックします。

5. [**サービスの選択**] で、アドインを作成する必要がある常設チャットサーバープールに対応するサービスを選びます。 アドインは、プール間で移動したり、異なるプール間で共有したりできません。

6. [**新しいアドイン**] で、次の操作を実行します。

   - [**名前**] に、新しいアドインの名前を指定します。

   - [**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。

7. [**コミット**] をクリックします。

## <a name="see-also"></a>関連項目

常設チャットサーバーの機能と機能について詳しくは、「skype [For Business server 2015 での常設チャットサーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)」、「skype for business server [2015 で](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)の常設チャットサーバーの展開」、「 [skype for Business server 2015 での常設チャットサーバーの管理](../../manage/persistent-chat/persistent-chat.md)」をご覧ください。


