---
title: クライアント バージョンの構成
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: 現在の環境でサポートするクライアントのバージョンのほか、バージョン ポリシーが定義されていないクライアントの既定のアクションも指定できます。これにより、現在の環境で使用するクライアント バージョンを制限し、複数のクライアント バージョンをサポートすることで発生するコストを制御できます。
ms.openlocfilehash: eb8dfa343c6ad9abc25008ff23f041ca9a2ef7e9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752296"
---
# <a name="client-version-configuration"></a>クライアント バージョンの構成

現在の環境でサポートするクライアントのバージョンのほか、バージョン ポリシーが定義されていないクライアントの既定のアクションも指定できます。これにより、現在の環境で使用するクライアント バージョンを制限し、複数のクライアント バージョンをサポートすることで発生するコストを制御できます。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**クライアント バージョンの構成**] ページでは、次のタスクを実行できます。

- 既定の (グローバル) **クライアント** バージョンの構成を編集します。

- 特定のサイトのクライアント バージョン構成を作成します。

- 既存のクライアント バージョン構成を有効または無効にします。

> [!NOTE]
> 匿名ユーザーをサイトに関連付けることはできないため、匿名ユーザーに適用されるのはグローバル レベルのポリシーだけです。

## <a name="ui-reference"></a>UI リファレンス

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

- **New** 特定のサイトのクライアント バージョン構成を作成できます。

- **編集** クライアント バージョン ポリシーのオプションを変更できます。 このオプションを使用すると、次の操作を実行できます。

  - **詳細の表示** このオプションは、クライアント バージョン構成のオプションを変更できるダイアログ ボックスを開きます。

  - **[すべて選択]** このオプションは、リスト内のすべてのクライアント バージョン構成を選択します。

  - **削除** このオプションは、選択したクライアント バージョン構成をすべて削除します。

- **更新** クライアント バージョン構成リストを更新して、すべてのクライアント バージョン構成のオプションの状態を確認できます。

クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)」を参照してください。クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)」を参照してください。