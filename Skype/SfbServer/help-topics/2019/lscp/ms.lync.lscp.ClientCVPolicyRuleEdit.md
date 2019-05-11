---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。
ms.openlocfilehash: 918d32b82a3f4fffddccdccc8ffe9671ad4b8a15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891881"
---
# <a name="client-version-rule"></a>クライアント バージョン ルール

クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。

- クライアント バージョン ポリシーに新しいルールを追加する。

- 既存のクライアント バージョン ポリシーを構成するルールを変更する。

## <a name="ui-reference"></a>UI リファレンス

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

- **ユーザー エージェント**クライアントの種類を一覧から選択できます。 次の表は、ユーザー エージェントのコードを定義します。 このリストには、レガシ クライアントの種類、それらの一部がサポートされていませんが含まれています。

|**クライアント名**|**ユーザー エージェント**|
|:-----|:-----|
|Lync 2013 では、Lync 2010 では、Office Communicator  <br/> |OC  <br/> |
|Lync Web アプリケーションでは、Communicator Web Access  <br/> |CWA  <br/> |
|Office Communicator の電話、Lync の電話のエディション  <br/> |OCPhone  <br/> |
|Communicator Phone Edition プラットフォーム  <br/> |CPE  <br/> |
|統合コミュニケーション プラットフォーム  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting アドイン  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|リアルタイム通信クライアント  <br/> |RTC  <br/> |
|IPad の Lync 2010  <br/> |iPadLync  <br/> |
|IPhone の Lync 2010  <br/> |iPhoneLync  <br/> |
|Windows Phone の Lync 2010  <br/> |WPLync  <br/> |
|Nokia の Lync 2010  <br/> |NokiaLync  <br/> |
|Android の Lync 2010  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **バージョン番号**次のフィールドにバージョン番号を指定するか、クライアントのバージョン番号を示すためにワイルドカードを使用できます。

  - **メジャー バージョン**主要なリリースのクライアントに対応する番号を指定します。

  - **マイナー バージョン**クライアントのマイナー リリースに対応する番号を指定します。

  - **ビルド**クライアントのメジャーおよびマイナー リリースに対応するビルド番号を指定します。

  - **更新**クライアントの更新のリリースに対応する番号を指定します。

- **比較演算**上記の手順で指定したクライアント バージョンの一致操作を指定できます。 次の操作を紹介します。

  - **[同じ]**

  - **[等しくない]**

  - **[より新しい]**

  - **[より新しいか同じ]**

  - **[より古い]**

  - **[より古いか同じ]**

- **アクション**上記の手順で条件が満たされたときに実行するアクションを指定することができます。 次の操作を紹介します。

  - **許可します。** ログオンするクライアントを使用できます。

  - **許可およびアップグレード**ログオンし、Windows Server の更新サービスまたは Microsoft Update から更新を受信するクライアントを使用できます。 この操作は、 **OC**のユーザー エージェントが選択した場合のみ利用可能です。

    > [!NOTE]
    > このアクションを選択すると、次にユーザーがビジネスのための Skype にサインインを表示する通知が発生します。 この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。 混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。

  - **URL を許可します。** により、クライアントがログオンして、別のクライアント バージョンをダウンロードする場所についてのメッセージが表示されます。 [**URL**] フィールドで URL を指定します。

  - **ブロック**クライアントがログオンできないようにします。

  - **ブロックおよびアップグレード**クライアントがログオンできないようにし、クライアントが Windows Server の更新サービスまたは Microsoft Update から更新を受信することができます。 この操作は、 **OC**のユーザー エージェントが選択した場合のみ利用可能です。

  - [**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。

クライアントとクライアントのバージョン間での相互運用性に関する詳細については、計画ドキュメントの[クライアントの相互運用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)を参照してください。 クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。

