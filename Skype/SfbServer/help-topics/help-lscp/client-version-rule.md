---
title: クライアント バージョン ルール
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
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: 4c46a93e46e1e07865a466a666a450a766c6897e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103453"
---
# <a name="client-version-rule"></a>クライアント バージョン ルール

クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。

- クライアント バージョン ポリシーに新しいルールを追加する。

- 既存のクライアント バージョン ポリシーを構成するルールを変更する。

## <a name="ui-reference"></a>UI リファレンス

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

- **ユーザー エージェント** リストからクライアントの種類を選択できます。 次の表は、ユーザー エージェント コードを定義します。

|**クライアント名**|**ユーザー エージェント**|
|:-----|:-----|
|Lync 2013、Lync 2010、Office Communicator  <br/> |OC  <br/> |
|Lync Web App、Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition プラットフォーム  <br/> |CPE  <br/> |
|統合コミュニケーション プラットフォーム  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting アドイン  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|リアルタイム通信クライアント  <br/> |RTC  <br/> |
|Lync 2010 for iPad  <br/> |iPadLync  <br/> |
|Lync 2010 for iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 for Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 for Nokia  <br/> |NokiaLync  <br/> |
|Android 用 Lync 2010  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **バージョン番号** 次のフィールドのバージョン番号を指定するか、ワイルドカードを使用してクライアントのバージョン番号を示します。

  - **メジャー バージョン** クライアントのメジャー リリースに対応する番号を指定します。

  - **マイナー バージョン** クライアントのマイナー リリースに対応する番号を指定します。

  - **ビルド** クライアントのメジャー リリースとマイナー リリースに対応するビルド番号を指定します。

  - **更新** クライアントの更新されたリリースに対応する番号を指定します。

- **比較操作** 前の手順で指定したクライアント バージョンに一致する操作を指定できます。 次の操作を使用できます。

  - **同じ**

  - **異なる**

  - **より新しい**

  - **以上**

  - **より古い**

  - **以前**

- **アクション** 前の手順の条件が満たされた場合に実行するアクションを指定できます。 次のアクションを使用できます。

  - **許可する** クライアントにログオンを許可します。

  - **許可とアップグレード** クライアントが Windows Server Update Service または Microsoft Update からログオンして更新プログラムを受信できます。 このアクションは、ユーザー エージェント **OC** が選択されている場合にのみ使用できます。

    > [!NOTE]
    > このアクションを選択すると、ユーザーが次に Skype for Business にサインインすると、通知が表示されます。 この通知では、更新プログラムがある場合、Windows Server Update Service または Microsoft Update にまだリリースされていなくても、更新プログラムを利用できることが伝えられます。 混乱を避けるため、このアクションは更新プログラムが利用できるようになった後でのみ選択する必要があります。

  - **URL で許可する** クライアントがログオンし、別のクライアント バージョンをダウンロードする場所に関するメッセージを表示します。 [**URL**] フィールドで URL を指定します。

  - **ブロック** クライアントがログオンを防止します。

  - **ブロックとアップグレード** クライアントがログオンし、クライアントが Windows Server Update Service または Microsoft Update から更新プログラムを受け取るのを許可します。 このアクションは、ユーザー エージェント **OC** が選択されている場合にのみ使用できます。

  - [**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。

クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)」を参照してください。 クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)」を参照してください。