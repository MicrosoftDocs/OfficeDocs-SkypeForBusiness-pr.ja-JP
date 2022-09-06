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
ms.localizationpriority: medium
ms.prod: skype-for-business-itpro
description: このトピックでは、既存のSkype for Business ServerまたはExchange Serverのデプロイを最新バージョンに移行するか、オンラインまたはExchange Online Skype for Businessに移行する場合に考慮する必要がある事項について説明します。
ms.openlocfilehash: ace5151a9a1a910b12b7cba36340bd00f2e96874
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486992"
---
# <a name="plan-for-skype-for-business-server-and-exchange-server-migration"></a>Skype for Business Server と Exchange Server の移行の計画

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

このトピックでは、既存のSkype for Business ServerまたはExchange ServerデプロイをExchange Onlineに移行する際に考慮する必要がある事項について説明します。 移行できるものと、いつ移行できるかは、組織で既に設定されているものに大きく依存します。

## <a name="feature-changes-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 および Skype for Business Server 2019 の機能の変更

Exchange 2019 と Skype for Business Server 2019 では、サポートされている機能にいくつかの変更を加えています。

### <a name="unified-messaging-support-in-exchange-2019"></a>Exchange 2019 でのユニファイド メッセージングのサポート

ユニファイド メッセージング (UM) は、Exchange 2019 で非推奨になりました。 つまり、Exchange 2019 では次の機能が提供されなくなりました。

- ボイスメール
- 自動応答

Exchange 2013 または Exchange 2016 で UM サービスを展開し、Exchange 2019 にアップグレードする場合は、ボイスメールを Microsoft 365 または Office 365のMicrosoft クラウド ボイスメール サービスに移行する必要があります。 ボイスメールをクラウド ボイスメールに移行する場合は、[Exchange 2013/Exchange 2016 と Skype for Business 2015 を Exchange 2019 および Skype for Business 2019](#exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019) のセクションで確認してください。
> [!IMPORTANT]
> Exchange 2013 または Exchange 2016 サーバーのユーザーに UM 対応メールボックスがある場合は、Skype for Business サーバーを 2019 Skype for Business Serverにアップグレードし、ボイス メッセージングの停止を回避するためにユーザーを Exchange 2019 に移動しないでください。

### <a name="pbx-support-in-exchange-2019-and-skype-for-business-server-2019"></a>Exchange 2019 および Skype for Business Server 2019 での PBX サポート

クラウド ボイスメールは、Private Branch Exchanges (PBXs) にボイス メッセージング機能を提供しません。 EXCHANGE SERVERユニファイド メッセージング for PBX を使用していて、2019 年 Exchange Serverにアップグレードする場合は、[Exchange Team Blog](https://blogs.technet.microsoft.com/exchange/) で[セッション ボーダー コントローラーのサポートを中止](https://blogs.technet.microsoft.com/exchange/2018/04/24/new-date-for-discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging/)するために、ブログ投稿の「新しい日付」に記載されている 3 つのオプションのいずれかを採用Exchange Online必要があります。

### <a name="exchange-online-um-support-in-skype-for-business-server-2019"></a>Skype for Business Server 2019 での um サポートのExchange Online

Skype for Business Server 2019 では、EXCHANGE ONLINE UM から クラウド ボイスメールに移行します。 ユーザーが Skype for Business 2019 サーバーに移動されると、ホストされているボイスメール用に構成されると、クラウド ボイスメールの使用が自動的に開始されます。 現在 EXCHANGE ONLINE UM を使用している場合は、ユーザーを 2019 年 Skype for Business Serverに移動してクラウド ボイスメールの使用を開始する以外に何もする必要はありません。 ただし、次の点に注意する必要がある機能にいくつかの変更があります。

- 組織の自動応答は、EXCHANGE ONLINE UM での自動応答の代わりです。
- Outlook on the Web のユーザー ボイスメール設定は、クラウド ボイスメールには適用されません。

## <a name="on-premises-um-migration-scenarios"></a>オンプレミスの UM 移行シナリオ

ユーザーを Exchange 2019 と クラウド ボイスメールの両方に移行できるようにする次のシナリオがサポートされています。

- Exchange 2013/Exchange 2016 および Skype for Business Server 2015 から Exchange 2019、Skype for Business Server 2019
- Exchange 2013/Exchange 2016 を使用して 2015 Skype for Business Server 2019 にSkype for Business Serverする

次のシナリオでは、現在の展開の一部として PBX または SBC 構成が存在しない必要があり、オンプレミスの Exchange サーバーに UM が構成されていることを前提としています。 また、これらの各ソリューションは、オンプレミスのSkype for Business サーバーと Microsoft 365 またはOffice 365の間でハイブリッド展開を構成することを決定したことを前提としています。 Skype for Businessハイブリッドデプロイの詳細については、「[ハイブリッド接続を計画する](plan-hybrid-connectivity.md)」を参照してください。

### <a name="exchange-2013exchange-2016-and-skype-for-business-2015-to-exchange-2019-and-skype-for-business-2019"></a>Exchange 2013/Exchange 2016 および Skype for Business 2015 から Exchange 2019、Skype for Business 2019

このシナリオでは、既存の Exchange 2013、Exchange 2016、Skype for Business 2015 サーバーを Exchange 2019 および Skype for Business 2019 に移行します。

このトピックで前述したように、Exchange 2019 には UM サービスは含まれなくなりました。 つまり、Exchange 2019 に移行するすべてのメールボックスでは、クラウド ボイスメールを使用して、UM サービスによって提供された機能を置き換える必要があります。 Skype for Business Server 2019 と Microsoft 365 または Office 365間のハイブリッド展開を設定すると、これらの Exchange UM ボイスメール サービスが置き換クラウド ボイスメール。

ユーザーを Exchange 2019 および Skype for Business Server 2019 に移動する順序は、ボイスメール機能をすべてのユーザーが引き続き使用できるようにするために重要です。 ボイスメールが処理される場所は、Exchange メールボックスとSkype for Businessメールボックスとユーザーが配置されている場所によっても決まります。 次の表を見て、Exchange とSkype for Business Serverの組み合わせがサポートされ、ボイスメールが処理される場所を確認します。

| メールボックスの場所:            | Skype for Business Server 2015 のユーザー | Skype for Business Server 2019 のユーザー  |
|--------------------------------|-----------------------------------------|------------------------------------------|
| Exchange 2013/Exchange 2016    | Exchange UM                             | Exchange UM                              |
| Exchange 2019                  | サポート対象外                           | クラウド ボイスメール                          |

Skype for Business Server 2019 と Exchange 2019 への移行を開始する前に、次の点に注意してください。

- メールボックスを Exchange 2019 に移動する前に、少なくとも 1 つのSkype for Business 2019 サーバーを設定 **し**、そのサーバーにユーザーを移動する必要があります。 これを行わないと、それらのメールボックスがボイスメール メッセージを受信できなくなります。
- ボイスメールに送信された通話は、記録されるクラウド ボイスメールに転送されます。 通話が終了すると、ボイスメール メッセージがオンプレミスの Exchange 2019 サーバー上の受信者のメールボックスに送信されます。 インターネット接続がクラウド ボイスメールをサポートするのに十分かどうかを判断する場合は、この音声トラフィックを考慮する必要があります。

この移行を完了するための大まかな手順を次に示します。

1. Skype for Business Server 2019 を新しいサーバーにインストールして構成します。
2. 新しいSkype for Business 2019 サーバーを含めるハイブリッド 展開構成を更新します。
3. Exchange Server 2019 を新しいサーバーにインストールして構成します。
4. Skype for Business 2015 サーバーから Skype for Business 2019 サーバーにユーザーを移動します。
5. クラウド ボイスメールを使用するために、Skype for Business Server 2019 に移動した各ユーザーのホストボイスメール ポリシーを設定します。
6. Exchange 2013 または Exchange 2016 サーバーから Exchange 2019 サーバーにメールボックスを移動します。
7. 最後のユーザーがSkype for Business 2015 サーバーから移動された後で使用を停止します。
8. 最後のメールボックスがそれらのメールボックスから移動された後、Exchange 2013 または Exchange 2016 サーバーを使用停止します。


### <a name="skype-for-business-server-2015-to-skype-for-business-server-2019-with-exchange-2013exchange-2016"></a>Exchange 2013/Exchange 2016 を使用して 2015 Skype for Business Server 2019 にSkype for Business Serverする

このシナリオでは、既存の Skype for Business 2015 サーバーを 2019 Skype for Business Serverに移行しますが、Exchange 2013 または Exchange 2016 に残ります。

Skype for Business Server 2015 と Skype for Business Server 2019 が同じ組織に共存する場合、Exchange UM とクラウド ボイスメールとシームレスに連携して、ボイスメールが Exchange メールボックスに正しく配信されるようにします。 Exchange UM とクラウド ボイスメールのどちらがボイスメールを処理するかは、ユーザーが 2015 年Skype for Business Serverか 2019 年Skype for Business Serverかに依存します。

- ユーザーが Skype for Business Server 2015 に配置されている場合、Exchange UM はボイスメール メッセージを処理します。
- ユーザーが Skype for Business Server 2019 に配置されている場合、クラウド ボイスメールはボイスメール メッセージを処理します。

Exchange UM またはクラウド ボイスメールがボイスメール メッセージを処理するかどうかに関係なく、メッセージはユーザーの Exchange メールボックスに格納されます。

Skype for Business Server 2019 への移行を開始する前に、次の点に注意してください。

- ボイスメールに送信された通話は、記録されるクラウド ボイスメールに転送されます。 通話が終了すると、ボイスメール メッセージがオンプレミスの Exchange サーバー上の受信者のメールボックスに送信されます。 インターネット接続がクラウド ボイスメールをサポートするのに十分かどうかを判断する場合は、この音声トラフィックを考慮する必要があります。

この移行を完了するための大まかな手順を次に示します。

1. Skype for Business Server 2019 を新しいサーバーにインストールして構成します。
2. 新しいSkype for Business 2019 サーバーを含めるハイブリッド 展開構成を更新します。
3. Skype for Business 2015 サーバーから Skype for Business 2019 サーバーにユーザーを移動します。
4. クラウド ボイスメールを使用するために、Skype for Business Server 2019 に移動した各ユーザーのホストボイスメール ポリシーを設定します。
5. 最後のユーザーがSkype for Business 2015 サーバーから移動された後で使用を停止します。

