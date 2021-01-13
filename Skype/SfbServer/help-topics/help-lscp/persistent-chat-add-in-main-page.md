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
description: '[常設チャット] ページの [アドイン] セクションを使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、チャット ルームの会話機能拡張ウィンドウのクライアントに表示されます。 管理者は登録済みアドインの一覧にアドインを追加する必要があります。チャット ルームのマネージャー/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録済みのアドインの 1 つにルームを関連付ける必要があります。'
ms.openlocfilehash: ee747e12b4a6209d831588e68533531b0a7d95ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803797"
---
# <a name="persistent-chat-add-in-main-page"></a>常設チャット アドイン メイン ページ

[常設チャット] **ページの** [アドイン] セクション **を** 使用して、URL を常設チャット ルームに関連付けできます。 これらの URL は、チャット ルームの会話機能拡張ウィンドウのクライアントに表示されます。 管理者は登録済みアドインの一覧にアドインを追加する必要があります。チャット ルームのマネージャー/作成者は、ユーザーがクライアントでこのアップグレードを確認する前に、登録済みのアドインの 1 つにルームを関連付ける必要があります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインには、株価情報がチャット ルームに投稿され、拡張ウィンドウに株価履歴が表示される Silverlight アプリケーションを指す URL が含まれる場合があります。 また、OneNote 2013 の URL をアドインとしてチャット ルームに組み込み、"優先事項" や "今日のトピック" などの共有コンテキストを表示することもできます。

常設チャット ルーム用のアドインを作成するには [、「Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)で常設チャット ルーム用のアドインを構成する」を参照してください。 常設チャット管理者の場合は、コントロール パネルまたはカスタム コマンドレットを使用してアドインWindows PowerShellできます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**アドイン**] ページでは、次のタスクを実行できます。

- [Skype for Business Server 2015 での常設チャット ルームのアドインの構成](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. [スタート **] メニューから** Skype for Business Server コントロール パネルを選択するか、ブラウザー ウィンドウを開いて管理 URL を入力します。 コントロール パネルの起動に使用できるさまざまな方法の詳細については、「Lync Server 管理ツールを開く」 [を参照してください](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。

3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。

    複数の常設チャット サーバー プール展開の場合は、ドロップダウン リストから適切なプールを選択します。

4. [**アドイン**] ページで、[**新規**] をクリックします。

5. [ **サービスの選択]** で、アドインを作成する必要がある常設チャット サーバー プールに対応するサービスを選択します。 アドインをプール間で移動したり、複数のプールで共有したりすることはできません。

6. [**新規 アドイン**] で、次の操作を実行します。

   - [**名前**] に、新しいアドインの名前を指定します。

   - [**URL**] で、アドインに関連付ける URL を指定します。URL には http および https プロトコルのみを使用できます。

7. [**確定**] をクリックします。

## <a name="see-also"></a>関連項目

常設チャット サーバーの機能の詳細については [、「Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Deploy Persistent Chat Server in Skype for Business Server 2015,](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)and [Manage Persistent Chat Server in Skype for Business Server 2015」](../../manage/persistent-chat/persistent-chat.md)を参照してください。


