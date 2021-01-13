---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: 26f37c77886ac9f9fe7fb8d8680fb0dad642a9cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812377"
---
# <a name="client-version-rule"></a>クライアント バージョン ルール

クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。

- クライアント バージョン ポリシーに新しいルールを追加する。

- 既存のクライアント バージョン ポリシーを構成するルールを変更する。

## <a name="ui-reference"></a>UI リファレンス

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

- **ユーザー エージェント** 一覧からクライアントの種類を選択できます。 次の表では、ユーザー エージェント コードを定義します。 この一覧には従来のクライアントの種類が含まれていますが、その一部はサポートされなくなりました。

|**クライアント名**|**ユーザー エージェント**|
|:-----|:-----|
|Lync 2013、Lync 2010、Office Communicator  <br/> |OC  <br/> |
|Lync Web App、Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition、Office Communicator Phone  <br/> |OCPhone  <br/> |
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
|Lync 2010 for Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **バージョン番号** 次のフィールドのバージョン番号を指定するか、ワイルドカードを使用してクライアントのバージョン番号を示します。

  - **メジャー バージョン** クライアントのメジャー リリースに対応する番号を指定します。

  - **マイナー バージョン** クライアントのマイナー リリースに対応する番号を指定します。

  - **ビルド** クライアントのメジャー リリースとマイナー リリースに対応するビルド番号を指定します。

  - **Update** クライアントの更新されたリリースに対応する番号を指定します。

- **比較操作** 前の手順で指定したクライアント バージョンの照合操作を指定できます。 次の操作を使用できます。

  - **同じ**

  - **異なる**

  - **より新しい**

  - **以上**

  - **より古い**

  - **以前**

- **アクション** 前の手順の条件が満たされた場合に実行するアクションを指定できます。 次のアクションを使用できます。

  - **許可** クライアントのログオンを許可します。

  - **許可とアップグレード** クライアントがログオンし、Windows Server Update Service または Microsoft Update から更新プログラムを受信できます。 このアクションは、ユーザー エージェント **OC** が選択されている場合にのみ使用できます。

    > [!NOTE]
    > このアクションを選択すると、ユーザーが次に Skype for Business にサインインすると通知が表示されます。 この通知では、更新プログラムがある場合、Windows Server Update Service または Microsoft Update にまだリリースされていなくても、更新プログラムを利用できることが伝えられます。 混乱を避けるため、このアクションは更新プログラムが利用できるようになった後でのみ選択する必要があります。

  - **URL を使用して許可する** クライアントがログオンし、別のクライアント バージョンをダウンロードする場所に関するメッセージを表示できます。 [**URL**] フィールドで URL を指定します。

  - **ブロック** クライアントのログオンを防止します。

  - **ブロックとアップグレード** クライアントのログオンを防止し、クライアントが Windows Server Update Service または Microsoft Update から更新プログラムを受信できます。 このアクションは、ユーザー エージェント **OC** が選択されている場合にのみ使用できます。

  - [**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。

クライアントとクライアント バージョン間の相互運用性の詳細については、「計画」のドキュメントの「 [クライアント](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) の相互運用性」を参照してください。 クライアント バージョンの構成を扱う処理の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。

