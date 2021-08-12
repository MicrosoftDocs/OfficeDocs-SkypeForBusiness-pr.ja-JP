---
title: ユニファイド メッセージングExchange統合を計画Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: '概要: 2013 または 2016 年にSkype for Business ServerをExchangeしながら、このトピックを確認してください。'
ms.openlocfilehash: 68ae17e7a7c5f3b427323f1ea571337de264529fbee954c61f40fb8afe20d1a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349939"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>ユニファイド メッセージングExchange統合を計画Skype for Business

**概要:** 2013 年または 2016 年Skype for Business ServerにExchangeこのトピックを確認してください。

Skype for Business Serverユニファイド メッセージング (UM) Exchange統合をサポートし、ボイス メッセージングと電子メール メッセージングを単一のメッセージング インフラストラクチャに組み合わせて使用できます。 このExchange、Exchangeユニファイド メッセージング (UM) は、インストールおよび構成できるExchangeサーバーの役割の 1 つです。

2013 Microsoft Exchange Server 2016 では、EXCHANGEメールボックス サーバー上のサービスとして UM Exchange実行されます。 ユニファイド Skype for Business Server エンタープライズ VoIP展開では、ボイス メッセージングと電子メール メッセージングを 1 つのストアに結合し、ユーザーは電話 (Outlook Voice Access) またはコンピューターからアクセスできます。 ユニファイド メッセージングとユニファイド Skype for Business Serverは、通話応答、Outlook 音声アクセス、自動応答サービスをユーザーに提供するためにエンタープライズ VoIP。

> [!NOTE]
> ExchangeUM は、2019 Skype for Business Server 2019 と Skype for Business 2013 または Exchange 2016 Exchangeで使用できます。 Exchange 2019 年のサポートの変更により、Exchange UM の統合は、クラウド ボイスメール とクラウド の機能を重視自動応答されています。  詳細[については、「Plan クラウド ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」および[「Plan for Skype for Business Server移行Exchange Server」を](../../../sfbhybrid/hybrid/plan-um-migration.md)参照してください。


これらの機能を UM 展開でExchangeするには、次のいずれかを実行している必要があります。

- Microsoft Exchange Server 2010 または最新のサービス パック (Skype for Business Server 2015 のみ)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> ExchangeSkype for Business Server 2019 では、電話システム を使用してボイスメール メッセージを記録し、その記録をユーザーの Exchange メールボックスに残すユニファイド メッセージングは使用できなくなりました。 詳細については[、「プラン クラウド ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>統合ユニファイド メッセージングと統合メッセージングのSkype for Business Server

Skype for Business Server エンタープライズ VoIP Exchange ユニファイド メッセージング (UM) インフラストラクチャを使用して、通話応答、通話通知、音声アクセス (ボイス メールを含む)、自動応答サービスを提供します。

- **通話応答** 通話応答とは、通話に応答していない、またはビジー状態のユーザーに代わって音声メッセージを受信する機能です。 これには、個人用案内応答の再生、メッセージの記録、およびユーザーのメールボックスへの配信のキューに入るメッセージの送信が含まれます。このメッセージは、Exchange メールボックス サーバーに保存されます。

    発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。

- **Outlook Voice Access** Outlook Voice Access を使用すると、エンタープライズ VoIP ユーザーは、ボイス メールだけでなく、テレフォニー インターフェイスからのメール、予定表、連絡先などの Exchange 受信トレイにもアクセスできます。 サブスクライバー アクセス番号は、UM 管理者によってExchangeされます。

- **自動応答** 自動応答は、Exchange外のユーザーが会社の担当者に連絡するためにダイヤルできる電話番号を構成するために使用できる UM 機能です。 具体的には、外部からの発信者に音声でメニュー システムの操作を案内します。 使用可能なオプションの一覧は、UM 管理者Exchange UM サーバー Exchange構成されます。

- **FAX サービスと** UM Exchange FAX 機能が含まれています。この機能を使用すると、ユーザーは自分のメールボックスで受信 fax を受信Exchangeできます。 詳細については、次の[ドキュメントの](/previous-versions/office/exchange-server-2007/bb123911(v=exchg.80))「ユニファイド メッセージングMicrosoft Exchange Serverしてください。

    > [!NOTE]
    > Exchange UM サーバーによって提供される FAX サービスは、Microsoft Exchange Server 2010、Exchange 2010、Exchange 2013、または Exchange 2016 と統合された Skype for Business Server 展開では使用できません。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>オンプレミスユニファイド メッセージングのコンポーネントとトポロジSkype for Business Server

### <a name="exchange-server-components"></a>Exchange Server コンポーネント

「統合ユニファイド メッセージングと Skype for Business Server の機能」で説明されている Exchange UM 機能とサービスを組織内の[エンタープライズ VoIP](#features-of-integrated-unified-messaging-and-skype-for-business-server)ユーザーに提供するには、Microsoft Exchange メールボックス サーバーとクライアント アクセス サーバーを展開し、ユーザー メールボックスをホストし、電子メールとボイス メールの 1 つの保存場所を提供する必要があります。 ExchangeUM は、メールボックス サーバーとクライアント アクセス Exchangeサービスとして実行されます。

Microsoft Exchange Server Exchange 2010 の UM コンポーネントの詳細については、「Deploying On-Premises Exchange UM to Provide [Lync Server 2013 Preview Voice Mail」](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail)を参照してください。

### <a name="supported-topologies"></a>サポートされるトポロジ

同じフォレストSkype for Business Server複数Exchangeユニファイド メッセージング (UM) を展開できます。 展開が複数のフォレストにまたがる場合は、UM フォレストごとにExchange統合手順を実行Exchange必要があります。 さらに、各 Microsoft Exchange フォレストを構成して、SKYPE FOR BUSINESS SERVER フォレストと Skype for Business Server UM フォレストを信頼Exchangeする必要があります。 このフォレストの信頼に加えて、すべてのExchangeの UM 設定を、フォレスト内のユーザー オブジェクトSkype for Business Server必要があります。

Skype for Business Server UM 統合では、次のトポロジExchangeサポートされています。

- 単一のフォレスト

- 単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。 Skype for Business Server、Microsoft Exchangeユーザーはすべて同じドメインに存在します。

- 複数のドメイン (つまり、1 つ以上の子ドメインを持つルート ドメイン)。 Skype for Business Server、Microsoft Exchangeサーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。 ExchangeUM サーバーは、サポートするサーバー プールとは異なるドメインSkype for Business Server展開できます。

- 複数のフォレスト (すなわち、リソース フォレスト)。 Skype for Business Serverは 1 つのフォレストに展開され、ユーザーは複数のフォレストに分散されます。 ユーザーの UM Exchangeは、ユーザーのフォレストにレプリケートSkype for Business Serverがあります。

    > [!NOTE]
    > Exchange は複数のフォレストに展開できます。 各Exchangeは、ユーザー Exchange UM を提供するか、EXCHANGE UM をユーザーと同じフォレストに展開Skype for Business Server。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>オンプレミスユニファイド メッセージングとユニファイド メッセージングを統合するSkype for Business Server

次に示すのは、展開時に考慮するガイドラインとベスト プラクティスエンタープライズ VoIP。

> [!IMPORTANT]
> Exchangeユニファイド メッセージング (UM) は、UCMA 4 も使用している場合にのみ IPv6 をサポートします。

- サーバーまたはSkype for Business Server Standard Editionプールを展開します。

- スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。

- UM をExchangeするユニファイド メッセージング (UM) フォレストExchangeメールボックス サーバーの役割を展開Exchangeします。 サーバーの役割のインストールExchange詳細については、次のドキュメントMicrosoft Exchange Serverしてください。

    > [!IMPORTANT]
    > ユニファイド Exchange (UM) がインストールされている場合、自己署名証明書を使用するように構成されます。 自己署名証明書では、Skype for Business Server UM と Exchange UM が互いを信頼できないので、両方のサーバーが信頼する証明機関から別の証明書を要求する必要があります。

- UM Skype for Business Serverと Exchange UM が異なるフォレストにインストールされている場合は、Skype for Business Server フォレストと Skype for Business Server フォレストを信頼して各 Exchange フォレストを信頼Exchangeします。 また、Skype for Business Server フォレスト内Exchangeユーザー オブジェクトに対してユーザーの UM 設定を設定します (通常は、スクリプトまたはフォレスト間ツール (ID ライフサイクル マネージャー (ILM) など) を使用します。

- 必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。

- Outlook Voice Access および自動応答の有効な電話番号を取得します。

- Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合は、Exchange UM SIP URI ダイヤル プランと エンタープライズ VoIP ダイヤル プランの名前を調整します。

### <a name="deploying-redundant-exchange-um-servers"></a>冗長 Exchange UM サーバーの展開

> [!IMPORTANT]
> 組織用に構成する Exchange UM SIP URI ダイヤル プランごとに、Exchange UM サービスが実行されている少なくとも Exchange 2 台のサーバーを展開することをお勧めします。 拡張容量の提供に加えて、冗長サーバーを展開すると高可用性が提供されます。 サーバーに障害が発生した場合、Skype for Business Serverサーバーにフェールオーバーするように構成できます。

次に示すのは、Exchange UM の復元性を提供する構成例です。

**例 1: Exchange UM の復元性**

![ExchangeUM 復元の図](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

例 1 では、Exchange UM サーバー 1 と 2 がトゥクウィラ データ センターで有効にされ、Exchange UM サーバー 3 と 4 がダブリン のデータ センターで有効になっています。 トゥクウィラで Exchange UM が停止した場合、サーバー 1 とサーバー 2 のレコードがそれぞれサーバー 3 と 4 を指するように構成する必要があります。 ダブリンで EXCHANGE UM が停止した場合、サーバー 3 とサーバー 4 の DNS A レコードは、それぞれサーバー 1 とサーバー 2 を指するように構成する必要があります。

> [!NOTE]
> 例 1 では、Exchange UM サーバーごとに次のいずれかの証明書を割り当てる必要があります。サブジェクトの代替名 (SAN) にワイルドカードを含む証明書を使用するか、4 つの Exchange UM サーバーのそれぞれについて完全修飾ドメイン名 (FQDN) を SAN に入れる必要があります。

**例 2:Exchange UM の復元性**

![ExchangeUM 復元の図](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。 4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー3 と 4 は有効化されていません。 たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。

2013 年 2013 年にユニファイド メッセージングを有効または無効にする方法の詳細については、「Exchange Exchange [2013 UM](/exchange/checklist-integrate-exchange-2013-um-with-lync-server-exchange-2013-help)と Lync Server を統合する」を参照してください。 提供される情報は、同じ方法でSkype for Business Server。

2010 年 2010 年にユニファイド メッセージングを有効または無効にする方法のMicrosoft Exchange Serverを参照してください。

- [2010 年にユニファイド メッセージングを有効Exchange](/previous-versions/office/exchange-server-2010/aa997908(v=exchg.141))

- [Exchange 2010 でユニファイド メッセージングを無効にする](/previous-versions/office/exchange-server-2010/bb123529(v=exchg.141))

### <a name="exchange-server-2019"></a>Exchange Server 2019

ExchangeExchange 2019 を使用し、同等の機能が必要な場合は、「クラウド ボイスメール サービスの計画」で説明されている クラウド ボイスメール サービスを使用する必要がある場合、ユニファイド メッセージングは Exchange 2019[に存在](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)しなくなりました。


## <a name="see-also"></a>関連項目

[オンプレミスユニファイド メッセージングとユニファイド メッセージングを統合する展開プロセスSkype for Business](deployment-overview.md)