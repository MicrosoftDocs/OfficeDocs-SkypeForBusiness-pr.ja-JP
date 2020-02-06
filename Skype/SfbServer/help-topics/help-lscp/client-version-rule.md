---
title: クライアント バージョン ルール
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 870f0d46ff50b4fabab9b4f098cb569ae2c9ee82
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823060"
---
# <a name="client-version-rule"></a>クライアント バージョン ルール

クライアント バージョン ポリシーは、一連のクライアント バージョン ルールで構成されます。これらのルールでは、ユーザーが特定のクライアントおよびクライアント バージョンでログオンしようとしたときに実行するアクションが定義されています。

## <a name="tasks-you-can-perform"></a>実行できるタスク

[**新規 クライアント バージョンの構成**] または [**編集 クライアント バージョンの構成**] ページでは、次のタスクを実行できます。

- クライアント バージョン ポリシーに新しいルールを追加する。

- 既存のクライアント バージョン ポリシーを構成するルールを変更する。

## <a name="ui-reference"></a>UI リファレンス

以下は、ページ上のメニュー、コマンド、フィールド、およびプロパティについての説明です。

- **ユーザーエージェント**リストからクライアントの種類を選ぶことができます。 次の表は、ユーザーエージェントコードを定義しています。

|**クライアント名**|**ユーザー エージェント**|
|:-----|:-----|
|Lync 2013、Lync 2010、Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition、Office Communicator フォン  <br/> |OCPhone  <br/> |
|Communicator Phone Edition プラットフォーム  <br/> |CPE  <br/> |
|統合コミュニケーション プラットフォーム  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting アドイン  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|リアルタイム通信クライアント  <br/> |RTC  <br/> |
|Lync 2010 for iPad  <br/> |iPadLync  <br/> |
|Lync 2010 for iPhone  <br/> |iPhoneLync  <br/> |
|Windows Phone 版 Lync 2010  <br/> |WPLync  <br/> |
|Lync 2010 for Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 for Android  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |

- **バージョン番号**次のフィールドのバージョン番号を指定するか、ワイルドカードを使用してクライアントのバージョン番号を示すことができます。

  - **メジャーバージョン**クライアントのメジャーリリースに対応する番号を指定します。

  - **マイナーバージョン**クライアントのマイナーリリースに対応する番号を指定します。

  - **ビルド**クライアントのメジャーとマイナーのリリースに対応するビルド番号を指定します。

  - **更新**クライアントの更新されたリリースに対応する番号を指定します。

- **比較演算**前の手順で指定したクライアントバージョンの照合操作を指定できます。 次の操作を実行できます。

  - **[同じ]**

  - **[等しくない]**

  - **[より新しい]**

  - **[より新しいか同じ]**

  - **[より古い]**

  - **[より古いか同じ]**

- **操作**前の手順の条件が満たされたときに実行するアクションを指定できます。 次の操作を実行できます。

  - **許可**クライアントがログオンできるようにします。

  - **許可とアップグレード**クライアントが Windows Server Update Service または Microsoft Update からログオンして更新プログラムを受信できるようにします。 この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。

    > [!NOTE]
    > このアクションを選ぶと、次回ユーザーが Skype for Business にサインインしたときに通知が表示されます。 この通知では、Windows Server Update Service または Microsoft Update に更新がまだリリースされていなくても、更新が利用できるようになったことが伝えられます。 混乱を避けるため、このアクションは必ず更新が利用できるようになってから選択する必要があります。

  - **URL で許可**クライアントがログオンして、別のクライアントバージョンをダウンロードする場所に関するメッセージを表示することを許可します。 [**URL**] フィールドで URL を指定します。

  - **ブロック**クライアントがログオンできないようにします。

  - **ブロックとアップグレード**クライアントがログオンし、Windows Server Update Service または Microsoft Update から更新プログラムを受信できるようにします。 この操作は、ユーザーエージェント**OC**が選択されている場合にのみ使用できます。

  - [**URL を使用した禁止**]   クライアントがログオンし、他のクライアント バージョンをダウンロードする場所についてのメッセージを表示することを禁止します。[**URL**] フィールドで URL を指定します。

クライアントとクライアント バージョンの間の相互運用性の詳細については、「計画」のドキュメントの「[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)」を参照してください。クライアント バージョンの構成の使用の詳細については、「操作」のドキュメントの「[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)」を参照してください。

