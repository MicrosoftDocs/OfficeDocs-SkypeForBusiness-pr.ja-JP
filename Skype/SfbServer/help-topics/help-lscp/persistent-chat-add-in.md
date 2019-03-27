---
title: 常設チャット アドイン
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 永続的なチャット ルームの Url に関連付けるには、永続的なチャット ページの追加のセクションを使用できます。 これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。 管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。
ms.openlocfilehash: 8cac9a89bcccc66459d0663f9211d22c173f94a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878822"
---
# <a name="persistent-chat-add-in"></a>常設チャット アドイン

永続的なチャット ルームの Url に関連付けるには、**永続的なチャット**ページの**追加の**セクションを使用できます。 これらの URL は、チャット ルームにいるクライアントの会話拡張機能ウィンドウに表示されます。 管理者が登録済みアドインの一覧にアドインを追加し、チャット ルームのマネージャー/作成者が登録済みアドインの 1 つにルームを関連付けると、ユーザーはクライアントでこのアップグレードを表示できるようになります。

アドインは、ルーム内でのエクスペリエンスを拡張するために使用されます。 一般的なアドインでは、株価情報は、チャット ルームがポストされ、拡張機能のウィンドウで株価履歴を表示しますを傍受した Silverlight アプリケーションを指す URL をなどがあります。 チャット ルームに OneNote 2013 の URL をアドインとして埋め込んで、"優先事項" や "今日のトピック" などの共有コンテキストを組み込むこともできます。

永続的なチャット ルームのアドインを作成するには、[ビジネス サーバー 2015 の Skype での永続的なチャット ルームの設定 - アドイン](../../manage/persistent-chat/configure-add-ins.md)を参照してください。 永続的なチャットの管理者は、コントロール パネルまたは Windows PowerShell コマンドレットを使用してアドインを作成します。

## <a name="tasks-that-you-can-perform"></a>実行できるタスク

[**アドイン**] ページでは、次のタスクを実行できます。

- [Skype for Business Server 2015 での常設チャット ルームのアドインの構成](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>チャット ルームのアドインを構成するには

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

1. CsPersistentChatAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. **[スタート**] メニューから、Skype ビジネス サーバーのコントロール パネルのまたはブラウザー ウィンドウを開きし、管理 URL を入力します。 コントロール パネルの起動に使用できるさまざまな方法の詳細については、「[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)」を参照してください。

3. 左側のナビゲーション バーで [**常設チャット**] をクリックして、[**アドイン**] をクリックします。

    複数の永続的なチャット サーバー プールの展開には、ドロップ ダウン リストから適切なプールを選択します。

4. [**アドイン**] ページで、[**新規**] をクリックします。

5. [**サービスの選択**] では、アドインを作成する必要がある永続的なチャット サーバー プールに対応するサービスを選択します。 アドインは、プール間で移動したり、異なるプール間で共有したりできません。

6. [**新しいアドイン**] で、次の操作を実行します。

   - [**名前**] に、新しいアドインの名前を指定します。

   - [**URL**] に、アドインに関連付ける URL を指定します。URL には、http および https プロトコルのみを使用できます。

7. [**コミット**] をクリックします。

## <a name="see-also"></a>関連項目

持続チャット サーバーで永続的なチャット サーバーの機能と機能に関する詳細は、[ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[ビジネス サーバー 2015 の Skype で永続的なチャット サーバーを展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)、および管理を[参照してください。ビジネス サーバー 2015 の Skype で](../../manage/persistent-chat/persistent-chat.md)。


