---
title: クライアント バージョン ポリシー [新規の作成] または [既存の編集]
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server 2015 に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。 クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。
ms.openlocfilehash: 614719a4d0152df4e451793e4845e7a6f72a59cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095611"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>クライアント バージョン ポリシー: 新規作成または現在の形式のままで編集

現在の環境でサポートするクライアントのバージョンを指定できます。 バージョンが異なる 2 つのクライアントが対話する場合、機能によっては一方のクライアントでは使用できても、他方のクライアントでは使用できないことがあります。 Skype for Business Server 2015 に含まれる機能を最も有効に利用し、全体的なユーザー エクスペリエンスを向上させるために、クライアント バージョン フィルターを使用して、環境で使用されるクライアント バージョンを制限できます。 クライアント バージョン フィルターを使用すると、複数バージョンのクライアントをサポートすることによって発生するコストを抑えることもできます。

> [!IMPORTANT]
> フィルターは、優先順にリストされます。たとえば、バージョン 1.5 を実行するクライアントに接続を許可するフィルターの後に、2.0 より古いバージョンを実行するクライアントを禁止するフィルターを設定した場合、最初のフィルターが優先されるため、バージョン 1.5 を実行するクライアントの接続が許可されます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新しいクライアント バージョン ポリシーの作成**] または [**編集 クライアント バージョン ポリシー**] ページでは、次のタスクを実行できます。

- クライアント バージョン ポリシーの名前や説明を追加または変更します。

- クライアント バージョン ポリシーのクライアント バージョン ルールを追加または変更します。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。

- **スコープ** クライアント バージョン ポリシーのスコープ (サイト、プール、またはユーザー) を識別します。

- **名前** クライアント バージョン ポリシーの名前を追加または変更できます。

- **説明** [クライアント バージョン ポリシー] ページの一覧で、ポリシーの識別に役立つ説明を追加できます。

- **New** 新しいクライアント バージョン ルールをポリシーに追加できます。

- **詳細の表示** このオプションは、クライアント バージョン ルールのオプションを変更できるダイアログ ボックスを開きます。

- **削除** このオプションは、選択したクライアント バージョン ルールをポリシーから削除します。

- **上下の矢印** このオプションは、選択したクライアント バージョン ルールを優先度で上下に移動します。 ルールは、一覧表示された順序で処理されます。

クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)」を参照してください。 クライアント バージョン ポリシーの操作の詳細については、「操作」のドキュメントの「[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)」を参照してください。