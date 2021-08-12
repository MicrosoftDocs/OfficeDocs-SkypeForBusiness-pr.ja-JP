---
title: Skype for Business Server と Exchange Server の移行の計画
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
description: このトピックでは、既存の Skype for Business Server または Exchange Server 展開を最新バージョンに移行する場合、または Skype for Business Online または Exchange Online に移行する場合に考慮する必要がある点について説明します。
ms.openlocfilehash: e933f1754023daa0991961204224176c34254f7821168eedbc30956c0188410a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341073"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Skype for Business Server と Exchange Server の移行の計画

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

このトピックでは、既存の展開を移行する際に考慮する必要がある点についてSkype for Business Server、Exchange Server展開を移行Exchange Online。 移行できる内容と、組織で既に設定されている内容に大きく依存する場合。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>2019 年Exchange 2019 年および 2019 年Skype for Business Server機能の変更

2019 Exchange 2019 年および 2019 年Skype for Business Server、サポートする機能にいくつかの変更を加えます。

### <a name="unified-messaging-support-in-exchange-2019"></a>ユニファイド メッセージングのサポート (Exchange 2019)

ユニファイド メッセージング (UM) は、2019 年Exchangeされました。 つまり、2019 Exchange機能は提供されなくなりました。

- ボイスメール
- 自動応答

Exchange 2013 または Exchange 2016 の UM サービスで UM 役割を展開し、Exchange 2019 にアップグレードする場合は、ボイスメールを Microsoft 365 または Office 365 の Microsoft クラウド ボイスメール サービスに移行する必要があります。 ボイスメールを クラウド ボイスメール に移行する場合は、Exchange [2013/Exchange 2016 および Skype for Business 2015 から Exchange 2019 および Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019)セクションを参照してください。
> [!IMPORTANT]
> Exchange 2013 または Exchange 2016 サーバーのユーザーに UM が有効なメールボックスがある場合は、Skype for Business サーバーを Skype for Business Server 2019 にアップグレードし、ボイス メッセージングの停止を回避するためにユーザーを移動する前に、それらを Exchange 2019 に移動しないようにしてください。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>2019 年Exchange 2019 年および 2019 年Skype for Business Server PBX のサポート

クラウド ボイスメールは、プライベート ブランチ エクスチェンジ (PBX) にボイス メッセージング機能を提供しない。 pbx 用 Exchange Server ユニファイド メッセージングを使用している場合に、Exchange Server 2019 にアップグレードする場合は、Exchange チーム ブログの[Exchange Online](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)ユニファイド メッセージングのセッション ボーダー コントローラーのサポートを中止するためのブログ投稿 「新しい日付」に記載されている 3 つのオプションのいずれかを採用する必要[](https://blogs.technet.microsoft.com/exchange/)があります。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Exchange Online2019 年の UM サポートSkype for Business Server 2019

2019 Skype for Business Server 2019 では、UM から Exchange Onlineに移行クラウド ボイスメール。 ユーザーが Skype for Business 2019 年 2019 年のサーバーに移動すると、ホストされたボイスメール用に構成クラウド ボイスメール自動的に使用が開始されます。 現在 Exchange Online UM を使用している場合は、ユーザーを Skype for Business Server 2019 に移動して クラウド ボイスメール の使用を開始する以外に何もする必要はありません。 ただし、次の点に注意する必要がある機能にいくつかの変更があります。

- 組織自動応答は、UM の自動応答のExchange Onlineです。
- Web 上の Outlookボイスメール設定は、ユーザーのボイスメールにクラウド ボイスメール。

## <a name="on-premises-um-migration-scenarios"></a>オンプレミスの UM 移行シナリオ

2019 年と 2019 年の両方にユーザーを移行し、Exchangeに移行クラウド ボイスメール。

- Exchange 2013/Exchange 2016 および Skype for Business Server 2015 ~ Exchange 2019 および Skype for Business Server 2019
- Skype for Business Server 2015 ~ Skype for Business Server 2019 Exchange 2013/Exchange 2016

次のシナリオでは、現在の展開の一部として PBX または SBC 構成が存在し、オンプレミスのサーバーで UM が構成されていることを前提Exchangeがあります。 また、これらの各ソリューションでは、オンプレミスのサーバーとサーバー間のハイブリッド展開を構成することを決定Skype for Business、Microsoft 365またはOffice 365。 ハイブリッド展開の詳細については、「Skype for Businessハイブリッド接続を計画[する」を参照してください](plan-hybrid-connectivity.md)。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 および Skype for Business 2015 ~ Exchange 2019 および Skype for Business 2019

このシナリオでは、既存の Exchange 2013、Exchange 2016、Skype for Business 2015 サーバーを Exchange 2019 および Skype for Business 2019 に移行します。

このトピックで前述したように、2019 Exchange UM サービスは含まなくなりました。 つまり、Exchange 2019 に移動するメールボックスの場合は、クラウド ボイスメール を使用して UM サービスによって提供された機能を置き換える必要があります。 2019 年 2019 Skype for Business Server と Microsoft 365 または Office 365 の間にハイブリッド展開をセットアップすると、クラウド ボイスメール はこれらの UM ボイスメール サービスExchange置き換わっています。

2019 年および Exchange Skype for Business Server 2019 年にユーザーを移動する順序は、ボイスメール機能をすべてのユーザーが利用できる状態に維持するために重要です。 ボイスメールの処理場所は、メールボックスとユーザー Exchange Skype for Business場所によっても決まります。 次の表を参照して、サポートされているボイスメールとExchangeとSkype for Business Serverの組み合わせを確認します。

| メールボックスは次の場所に位置します。            | ユーザーが 2015 年Skype for Business Server | ユーザーが 2019 Skype for Business Server  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | サポートされていません                           | クラウド ボイスメール                          |

2019 年および 2019 年Skype for Business Server 2019 年Exchange移行を開始する前に、次の点に注意してください。

- クラウドボイスメールは、GA での組織自動応答サポートされていません。 メールボックスを クラウド ボイスメール に移動して自動応答を使用して引き続き利用するには、UM の役割またはサービスを実行している少なくとも 1 つの Exchange 2013 または Exchange 2016 サーバーを保持する必要があります。
- メールボックスを 2019 年 2019 年に移動する前に、少なくとも 1 Skype for Business 2019 サーバーをセットアップし、そのサーバーにユーザーを移動するExchangeがあります。 そうしない場合、これらのメールボックスはボイスメール メッセージを受信できません。
- ボイスメールに送信された通話は、クラウド ボイスメールに転送されます。 通話が終了すると、ボイスメール メッセージが 2019 サーバー上のオンプレミスの受信者のメールボックスExchangeされます。 インターネット接続がインターネット接続をサポートするのに十分かどうかを判断する際には、この音声トラフィックを考慮クラウド ボイスメール。

この移行を完了するための高レベルの手順を次に示します。

1. 新しいサーバーにSkype for Business Server 2019 をインストールして構成します。
2. ハイブリッド展開構成を更新して、新しいサーバーを 2019 Skype for Businessします。
3. 新しいサーバーにExchange Server 2019 をインストールして構成します。
4. ユーザーを 2015 Skype for Business 2019 サーバーに移動Skype for Businessします。
5. 2019 年から 2019 年に移動した各ユーザー Skype for Business Serverボイスメール ポリシーを設定して、クラウド ボイスメール。
6. メールボックスを 2013 Exchange 2016 Exchange 2019 サーバーに移動Exchangeします。
7. 最後のユーザー Skype for Businessした後、2015 サーバーからサーバーを使用停止します。
8. 最後のメールボックスExchangeした後、2013 Exchange 2013 または 2016 サーバーの使用を停止します。

    > [!IMPORTANT]
    > 自動応答に依存している場合は、2013 年または 2016 年Exchange 2016 年Exchangeを実行して使用可能にしてください。

### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Skype for Business Server 2015 ~ Skype for Business Server 2019 Exchange 2013/Exchange 2016

このシナリオでは、既存の Skype for Business サーバーを Skype for Business Server 2019 に移行しますが、Exchange 2013 または Exchange 2016 に残ります。

2015 Skype for Business Server Skype for Business Server 2019 が同じ組織に共存する場合、Exchange UM と クラウド ボイスメール とシームレスに連携して、ボイスメールが Exchange メールボックスに正しく配信されるようにします。 UM または Exchangeがボイスクラウド ボイスメールを処理するかどうかは、ユーザーが 2015 年または 2019 年Skype for Business ServerにSkype for Business Serverされます。

- ユーザーが 2015 年 2015 年Skype for Business Server場合、UM Exchangeボイスメール メッセージが処理されます。
- ユーザーが 2019 年 2019 年Skype for Business Server場合、クラウド ボイスメールメッセージが処理されます。

UM またはメール メッセージExchangeクラウド ボイスメールに関係なく、メッセージはユーザーのメールボックスにExchangeされます。

2019 年から 2019 年Skype for Business Server移行を開始する前に、次の点に注意してください。

- クラウドボイスメールは、GA での組織自動応答サポートされていません。 メールボックスを クラウド ボイスメール に移動して自動応答を使用して引き続き利用するには、UM の役割またはサービスを実行している少なくとも 1 つの Exchange 2013 または Exchange 2016 サーバーを保持する必要があります。
- ボイスメールに送信された通話は、クラウド ボイスメールに転送されます。 通話が終了すると、ボイスメール メッセージがオンプレミスサーバー上の受信者のメールボックスExchangeされます。 インターネット接続がインターネット接続をサポートするのに十分かどうかを判断する際には、この音声トラフィックを考慮クラウド ボイスメール。

この移行を完了するための高レベルの手順を次に示します。

1. 新しいサーバーにSkype for Business Server 2019 をインストールして構成します。
2. ハイブリッド展開構成を更新して、新しいサーバーを 2019 Skype for Businessします。
3. ユーザーを 2015 Skype for Business 2019 サーバーに移動Skype for Businessします。
4. 2019 年から 2019 年に移動した各ユーザー Skype for Business Serverボイスメール ポリシーを設定して、クラウド ボイスメール。
5. 最後のユーザー Skype for Businessした後、2015 サーバーからサーバーを使用停止します。

    > [!IMPORTANT]
    > 自動応答に依存している場合は、2013 年または 2016 年Exchange 2016 年Exchangeを実行して使用可能にしてください。
