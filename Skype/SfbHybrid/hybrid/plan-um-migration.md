---
title: Skype for Business Server および Exchange Server の移行を計画する
ms.reviewer: ''
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
localization_priority: Normal
ms.prod: skype-for-business-itpro
description: このトピックでは、既存の Skype for Business Server または Exchange Server の展開を最新バージョンまたは Skype for Business Online または Exchange Online に移行する場合に考慮する必要がある事項について説明します。
ms.openlocfilehash: ce2e0712c75e5aa052c7eff7667f09ff34c3908a
ms.sourcegitcommit: bb88ac0c9489bb47957e5ef1074b5df3126b6fdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42265612"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Skype for Business Server および Exchange Server の移行を計画する

このトピックでは、既存の Skype for Business Server または Exchange Server の展開を最新バージョンまたは Skype for Business Online または Exchange Online に移行する場合に考慮する必要がある事項について説明します。 移行できる対象は、組織内で既にセットアップされているものによって大きく異なります。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 および Skype for Business Server 2019 での機能の変更点

Exchange 2019 と Skype for Business Server 2019 では、サポートされている機能にいくつかの変更を加えています。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 でのユニファイドメッセージングのサポート

ユニファイドメッセージング (UM) は、Exchange 2019 で廃止されました。 これは、Exchange 2019 が次の機能を提供しなくなったことを意味します。

- ボイスメール
- 自動応答

Exchange 2013 または exchange 2016 の UM サービスに UM の役割を展開していて、Exchange 2019 にアップグレードする場合は、ボイスメールを Office 365 の Microsoft Cloud ボイスメールサービスに移行する必要があります。 ボイスメールをクラウドボイスメールに移行する場合は、以下の「 [exchange 2013/exchange 2016 And skype For business 2015 To exchange 2019 And skype](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) for business 2019」セクションを参照してください。
> [!IMPORTANT]
> Exchange 2013 または Exchange 2016 サーバーのユーザーが UM が有効なメールボックスを持っている場合は、Skype for business サーバーを Skype for business Server の2019にアップグレードし、ユーザーをそれらのサーバーに移動してボイスメッセージングが停止しないようにする前に、exchange 2019 に移行しないでください。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 および Skype for Business Server 2019 での PBX のサポート

クラウドボイスメールは、構内交換機 (Pbx) に対してボイスメッセージング機能を提供しません。 Pbx 用に Exchange Server ユニファイドメッセージングを使用していて、Exchange Server 2019 にアップグレードする場合は、「ブログ投稿の新開始日」に記載されている3つのオプションのいずれかを使用して、exchange [Online ユニファイドメッセージングの「中止 support For Session Border Controllers in](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/) Exchange [Team blog](https://blogs.technet.microsoft.com/exchange/)」をご覧ください。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 での Exchange Online UM のサポート

Skype for Business Server 2019 では、Exchange Online UM からクラウドボイスメールに移行しています。 ユーザーが Skype for Business 2019 サーバーに移動すると、ホスト型ボイスメール用に構成されている場合、クラウドボイスメールの使用が自動的に開始されます。 現在 Exchange Online UM を使用している場合、クラウドボイスメールの使用を開始するには、ユーザーを Skype for Business Server 2019 に移動する以外に行う必要はありません。 ただし、認識しておく必要がある機能にはいくつかの変更があります。

- 組織の自動応答は、Exchange Online UM の自動応答に代わるものです。
- Web 上の Outlook でのユーザーボイスメールの設定は、クラウドボイスメールには適用されません。

## <a name="on-premises-um-migration-scenarios"></a>オンプレミスの UM 移行シナリオ

ユーザーを Exchange 2019 とクラウドボイスメールの両方に移行できるようにする次のシナリオをサポートしています。

- Exchange 2013/Exchange 2016 および Skype for Business Server 2015 から Exchange 2019 および Skype for business Server 2019
- Skype for business Server 2015 から Skype for business Server 2019 (Exchange 2013/Exchange 2016)

次のシナリオでは、現在の展開の一部として PBX または SBC 構成が存在しないこと、およびオンプレミスの Exchange サーバーで UM が構成されていることを前提としています。 これらの各ソリューションは、オンプレミスの Skype for Business サーバーと Office 365 との間でハイブリッド展開を構成することを前提としています。 Skype for Business ハイブリッド展開の詳細については、「 [Plan hybrid connectivity](plan-hybrid-connectivity.md)」を参照してください。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 および Skype for Business 2015 から Exchange 2019 および Skype for business 2019

このシナリオでは、既存の Exchange 2013、Exchange 2016、および Skype for business の2015サーバーを Exchange 2019 と Skype for Business の2019に移行します。

このトピックで前述したように、Exchange 2019 には UM サービスは含まれなくなりました。 これは、Exchange 2019 に移行するすべてのメールボックスに対して、UM サービスによって提供された機能をクラウドボイスメールを使用して置き換える必要があることを意味します。 Skype for Business Server 2019 と Office 365 との間でハイブリッド展開を設定すると、これらの Exchange UM ボイスメールサービスがクラウドボイスメールに置き換えられます。

ボイスメール機能をすべてのユーザーが引き続き利用できるようにするには、ユーザーを Exchange 2019 および Skype for Business Server 2019 に移動する順序が重要です。 また、ボイスメールが処理される場所は、Exchange と Skype for Business のメールボックスとユーザーが配置されている場所によって決まります。 次の表を参照して、Exchange と Skype for business サーバーのどの組み合わせがサポートされており、ボイスメールが処理されるかを確認します。

| メールボックスの場所:            | Skype for Business Server 2015 にあるユーザー | Skype for Business Server 2019 にあるユーザー  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | 非サポート                           | クラウド ボイスメール                          |

Skype for Business Server 2019 および Exchange 2019 への移行を開始する前に、次の点に注意してください。

- クラウドボイスメールは、GA 時に組織の自動応答をサポートしません。 クラウドボイスメールに移動されたメールボックスを引き続き自動応答で利用できるようにする場合は、UM の役割またはサービスを実行している Exchange 2013 または Exchange 2016 サーバーを少なくとも1つ保持する必要があります。
- Exchange 2019 にメールボックスを移動する前に、少なくとも1つの Skype for Business 2019 server をセットアップ**し、** ユーザーをそのサーバーに移動する必要があります。 そうしないと、それらのメールボックスはボイスメールメッセージを受信できなくなります。
- ボイスメールに送信された通話は、記録されるクラウドボイスメールに転送されます。 通話が終了すると、ボイスメールメッセージは社内 Exchange 2019 サーバー上の受信者のメールボックスに送信されます。 クラウドボイスメールをサポートするのにインターネット接続が十分であるかどうかを判断するには、この音声トラフィックを考慮する必要があります。

この移行を完了するための大まかな手順は次のとおりです。

1. 新しいサーバーに Skype for Business Server 2019 をインストールして構成します。
2. 新しい Skype for Business 2019 サーバーが含まれるように、ハイブリッド展開の構成を更新します。
3. Exchange Server 2019 を新しいサーバーにインストールして構成します。
4. Skype for business 2015 サーバーから Skype for Business 2019 サーバーにユーザーを移動します。
5. クラウドボイスメールを使用するには、Skype for Business Server 2019 に移動された各ユーザーのホストボイスメールポリシーを設定します。
6. Exchange 2013 または Exchange 2016 サーバーから Exchange 2019 サーバーにメールボックスを移動します。
7. 前回ユーザーが移動した後、Skype for Business 2015 サーバーの使用を停止します。
8. 最後のメールボックスが移動された後、Exchange 2013 または Exchange 2016 サーバーの使用を停止します。

    > [!IMPORTANT]
    > 自動応答に依存している場合は、少なくとも1つの Exchange 2013 または Exchange 2016 を実行し、使用可能にしておきます。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for business Server 2015 から Skype for business Server 2019 (Exchange 2013/Exchange 2016)

このシナリオでは、既存の Skype for Business 2015 サーバーを Skype for Business Server 2019 に移行しますが、Exchange 2013 または Exchange 2016 上に保持します。

Skype for business Server 2015 と Skype for business Server 2019 が同じ組織に共存する場合、Exchange UM とクラウドボイスメールを使用して、ボイスメールが確実に Exchange メールボックスに配信されるようにします。 Exchange UM またはクラウドボイスメールがボイスメールを処理するかどうかは、ユーザーが Skype for Business Server 2015 または Skype for Business Server 2019 上にあるかどうかによって決まります。

- ユーザーが Skype for Business Server 2015 上にある場合、Exchange UM はボイスメールメッセージを処理します。
- ユーザーが Skype for Business Server 2019 上にある場合、クラウドボイスメールはボイスメールメッセージを処理します。

Exchange UM またはクラウドボイスメールがボイスメールメッセージを処理するかどうかに関係なく、メッセージはユーザーの Exchange メールボックスに格納されます。

Skype for Business Server 2019 への移行を開始する前に、次の点に注意してください。

- クラウドボイスメールは、GA 時に組織の自動応答をサポートしません。 クラウドボイスメールに移動されたメールボックスを引き続き自動応答で利用できるようにする場合は、UM の役割またはサービスを実行している Exchange 2013 または Exchange 2016 サーバーを少なくとも1つ保持する必要があります。
- ボイスメールに送信された通話は、記録されるクラウドボイスメールに転送されます。 通話が終了すると、ボイスメールメッセージは社内 Exchange サーバー上の受信者のメールボックスに送信されます。 クラウドボイスメールをサポートするのにインターネット接続が十分であるかどうかを判断するには、この音声トラフィックを考慮する必要があります。

この移行を完了するための大まかな手順は次のとおりです。

1. 新しいサーバーに Skype for Business Server 2019 をインストールして構成します。
2. 新しい Skype for Business 2019 サーバーが含まれるように、ハイブリッド展開の構成を更新します。
3. Skype for business 2015 サーバーから Skype for Business 2019 サーバーにユーザーを移動します。
4. クラウドボイスメールを使用するには、Skype for Business Server 2019 に移動された各ユーザーのホストボイスメールポリシーを設定します。
5. 前回ユーザーが移動した後、Skype for Business 2015 サーバーの使用を停止します。

    > [!IMPORTANT]
    > 自動応答に依存している場合は、少なくとも1つの Exchange 2013 または Exchange 2016 を実行し、使用可能にしておきます。
