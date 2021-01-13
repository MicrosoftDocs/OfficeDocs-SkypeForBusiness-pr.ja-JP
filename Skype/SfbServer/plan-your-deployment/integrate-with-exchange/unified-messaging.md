---
title: Skype for Business での Exchange ユニファイド メッセージングの統合を計画する
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
description: '概要: Skype for Business Server と Exchange 2013 または 2016 の統合を計画する場合は、このトピックを確認してください。'
ms.openlocfilehash: 1ae93ebeda07fccf6c9019d5bb78c63f7c722192
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810117"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Skype for Business での Exchange ユニファイド メッセージングの統合を計画する

**概要:** Skype for Business Server と Exchange 2013 または 2016 の統合を計画する場合は、このトピックを確認してください。

Skype for Business Server は、ボイス メッセージングと電子メール メッセージングを単一のメッセージング インフラストラクチャに統合する Exchange ユニファイド メッセージング (UM) との統合をサポートしています。 Exchange では、Exchange ユニファイド メッセージング (UM) は、インストールおよび構成できるいくつかの Exchange サーバーの役割の 1 つです。

2013 Microsoft Exchange Server 2016 では、Exchange UM は Exchange メールボックス サーバー上のサービスとして実行されます。 Skype for Business Server エンタープライズ VoIP 展開の場合、ユニファイド メッセージングは音声メッセージングと電子メール メッセージングを 1 つのストアに結合し、ユーザーは電話 (Outlook Voice Access) またはコンピューターからアクセスできます。 ユニファイド メッセージングと Skype for Business Server が一緒に機能し、通話応答、Outlook Voice Access、および自動応答サービスをユーザーに提供エンタープライズ VoIP。

> [!NOTE]
> Skype for Business 2019 と Exchange 2013 または Exchange 2016 を統合する場合、Exchange UM は Skype for Business Server 2019 で引き続き使用できます。 Exchange 2019 のサポートの変更により、Exchange UM 統合は、クラウド ボイスメール機能とクラウド ボイスメール機能の使用を重視自動応答されています。  詳細 [については、「クラウド ボイスメール サービスの計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) 」と [「Skype for Business Server](../../../sfbhybrid/hybrid/plan-um-migration.md) の計画」および「Exchange Server移行」を参照してください。


これらの機能をオンプレミスの Exchange UM 展開でサポートするには、次のいずれかを実行する必要があります。

- Microsoft Exchange Server 2010 または最新のサービス パック (Skype for Business Server 2015 のみ)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016

> [!NOTE]
> 以前に知られている Exchange ユニファイド メッセージングは、Skype for Business Server 2019 では使用できなくなりました。Skype for Business Server 2019 では、電話システムを使用してボイスメール メッセージを録音し、その録音をユーザーの Exchange メールボックスに残します。 詳細 [については、「クラウド ボイスメール サービスを計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) する」を参照してください。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>統合ユニファイド メッセージングと Skype for Business Server の機能

Skype for Business Server エンタープライズ VoIP は、Exchange ユニファイド メッセージング (UM) インフラストラクチャを使用して、通話応答、通話通知、音声アクセス (ボイス メールを含む)、および自動応答サービスを提供します。

- **通話応答** 通話応答は、通話に応答しない、または通話中のユーザーの代わりに音声メッセージを受信します。 これには、個人用案内応答の再生、メッセージの録音、Exchange メールボックス サーバーに格納されているユーザーのメールボックスへの配信のためにキューに入れらるメッセージの送信が含まれます。

    発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。

- **Outlook Voice Access** Outlook Voice Accessユーザーエンタープライズ VoIPボイス メールだけでなく、電子メール、予定表、およびテレフォニー インターフェイスからの連絡先を含む Exchange 受信トレイにもアクセスできます。 サブスクライバー アクセス番号は、Exchange UM 管理者によって割り当てられます。

- **自動応答** 自動応答は、外部ユーザーがダイヤルして会社の担当者に連絡できる電話番号を構成するために使用できる Exchange UM 機能です。 具体的には、外部からの発信者に音声でメニュー システムの操作を案内します。 使用可能なオプションの一覧は、Exchange UM 管理者が Exchange UM サーバーで構成します。

- **FAX サービス** Exchange UM には、ユーザーが Exchange メールボックスで着信 FAX を受信できる FAX 機能が含まれています。 詳細については、以下の [ドキュメントの「](https://go.microsoft.com/fwlink/p/?linkId=135652) ユニファイド メッセージング」Microsoft Exchange Serverしてください。

    > [!NOTE]
    > Exchange UM サーバーによって提供される FAX サービスは、Microsoft Exchange Server 2010、Exchange 2010 と最新のサービス パック、Exchange 2013、または Exchange 2016 と統合された Skype for Business Server 展開では使用できません。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Skype for Business Server のオンプレミスユニファイド メッセージングのコンポーネントとトポロジ

### <a name="exchange-server-components"></a>Exchange Server コンポーネント

統合ユニファイド メッセージングと Skype for [Business Server](#features-of-integrated-unified-messaging-and-skype-for-business-server) の機能で説明されている Exchange UM の機能とサービスを組織内の エンタープライズ VoIP ユーザーに提供するには、ユーザー メールボックスをホストし、電子メールとボイス メールの単一の保存場所を提供する Microsoft Exchange メールボックス サーバーとクライアント アクセス サーバーを展開する必要があります。 Exchange UM は、Exchange メールボックス サーバーとクライアント アクセス サーバー上のサービスとして実行されます。

Microsoft Exchange Server 2010 の Exchange UM コンポーネントの詳細については [、「Deploying On-Premises Exchange UM to Provide Lync Server 2013 Preview Voice Mail](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx) 」を参照してください。

### <a name="supported-topologies"></a>サポートされるトポロジ

同じフォレストまたは複数のフォレストに Skype for Business Server と Exchange ユニファイド メッセージング (UM) を展開できます。 展開が複数のフォレストにまたがる場合は、Exchange UM フォレストごとに Exchange 統合手順を実行する必要があります。 さらに、Skype for Business Server フォレストと Skype for Business Server フォレストを信頼して各 Exchange UM フォレストを信頼する各 Microsoft Exchange フォレストを構成する必要があります。 このフォレストの信頼に加えて、Skype for Business Server フォレスト内のユーザー オブジェクトに対して、すべてのユーザーの Exchange UM 設定を設定する必要があります。

Skype for Business Server は、Exchange UM 統合のために次のトポロジをサポートしています。

- 単一のフォレスト

- 単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。 Skype for Business Server、Microsoft Exchange、およびユーザーはすべて同じドメインに存在します。

- 複数のドメイン (つまり、1 つ以上の子ドメインを持つルート ドメイン)。 Skype for Business Server および Microsoft Exchange サーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。 Exchange UM サーバーは、サポートする Skype for Business Server プールとは異なるドメインに展開できます。

- 複数のフォレスト (すなわち、リソース フォレスト)。 Skype for Business Server は 1 つのフォレストに展開され、ユーザーは複数のフォレストに分散されます。 ユーザーの Exchange UM 属性を Skype for Business Server フォレストにレプリケートする必要があります。

    > [!NOTE]
    > Exchange は複数のフォレストに展開できます。 各 Exchange 組織は Exchange UM をユーザーに提供するか、Exchange UM を Skype for Business Server と同じフォレストに展開できます。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>オンプレミスのユニファイド メッセージングと Skype for Business Server を統合するガイドライン

次に示すのは、展開時に考慮する必要があるガイドラインとベスト プラクティスエンタープライズ VoIP。

> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) は、UCMA 4 も使用している場合にのみ IPv6 をサポートします。

- Skype for Business Server Standard Edition サーバーまたはフロントエンド プールを展開します。

- スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。

- Exchange UM のユーザーを有効にする各 Exchange ユニファイド メッセージング (UM) フォレストに Exchange メールボックス サーバーの役割を展開します。 Exchange サーバーの役割のインストールの詳細については、以下のドキュメントMicrosoft Exchange Serverしてください。

    > [!IMPORTANT]
    > Exchange ユニファイド メッセージング (UM) をインストールすると、自己署名証明書を使用するように構成されます。 自己署名証明書を使用しても、Skype for Business Server と Exchange UM は互いを信頼できません。このため、両方のサーバーが信頼する証明機関から別の証明書を要求する必要があります。

- Skype for Business Server と Exchange UM が異なるフォレストにインストールされている場合は、Skype for Business Server フォレストと Skype for Business Server フォレストを信頼して各 Exchange フォレストを信頼する各 Exchange フォレストを構成します。 また、Skype for Business Server フォレスト内のユーザー オブジェクトにユーザーの Exchange UM 設定を設定します。通常は、スクリプトまたは Id Lifecycle Manager (ILM) などのフォレスト間ツールを使用します。

- 必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。

- Outlook Voice Access および自動応答の有効な電話番号を取得します。

- Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合は、Exchange UM SIP URI ダイヤル プランと エンタープライズ VoIP ダイヤル プランの名前を調整します。

### <a name="deploying-redundant-exchange-um-servers"></a>冗長 Exchange UM サーバーの展開

> [!IMPORTANT]
> 組織に構成する Exchange UM SIP URI ダイヤル プランごとに、Exchange UM サービスが実行されているサーバーを少なくとも 2 台展開することをお勧めします。 容量の拡張に加えて、冗長サーバーを展開すると高可用性が実現されます。 サーバー障害が発生した場合は、Skype for Business Server を別のサーバーにフェールオーバーするように構成できます。

次に示すのは、Exchange UM の復元性を提供する構成例です。

**例 1: Exchange UM の復元性**

![Exchange UM の復元の図](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

例 1 では、Exchange UM サーバー 1 と 2 が Dublin データ センターで有効にされ、Exchange UM サーバー 3 と 4 が Dublin データ センターで有効になります。 Exchange UM が Outagewila で停止した場合、サーバー 1 とサーバー 2 のドメイン ネーム システム (DNS) A レコードは、それぞれサーバー 3 とサーバー 4 を指するように構成する必要があります。 Dublin で Exchange UM が停止した場合、サーバー 3 とサーバー 4 の DNS A レコードは、それぞれサーバー 1 とサーバー 2 をポイントするように構成する必要があります。

> [!NOTE]
> 例 1 では、各 Exchange UM サーバーに次のいずれかの証明書を割り当てる必要があります。サブジェクトの代替名 (SAN) にワイルドカードを含む証明書を使用するか、4 つの Exchange UM サーバーの完全修飾ドメイン名 (FQDN) を SAN に入れる必要があります。

**例 2:Exchange UM の復元性**

![Exchange UM の復元の図](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。 4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー3 と 4 は有効化されていません。 たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。

Exchange 2013 でユニファイド メッセージングを有効または無効にする方法の詳細については  [、「Exchange 2013 UM](https://go.microsoft.com/fwlink/p/?LinkId=265372)と Lync Server の統合」を参照してください。 提供される情報は、Skype for Business Server にも同様に適用されます。

Microsoft Exchange Server 2010 でユニファイド メッセージングを有効または無効にする方法の詳細については、以下を参照してください。

- [Exchange 2010 でユニファイド メッセージングを有効にする](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Exchange 2010 でユニファイド メッセージングを無効にする](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange 2019 をお持ちで同等の機能が必要な場合は、「クラウド ボイスメール サービスの計画」で説明されているクラウド ボイスメール サービスを使用する必要[があります。](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)


## <a name="see-also"></a>関連項目

[オンプレミスのユニファイド メッセージングと Skype for Business を統合する展開プロセスの概要](deployment-overview.md)
