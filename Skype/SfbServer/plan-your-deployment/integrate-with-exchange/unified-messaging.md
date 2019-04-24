---
title: Skype for Business での Exchange ユニファイド メッセージング統合の計画
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: '概要: ビジネスのサーバーで Exchange 2013 または 2016 の Skype を統合するために計画するときにこのトピックを参照します。'
ms.openlocfilehash: 951b31e36290bda0d6bd171c4a7df8f6aa4ff337
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213946"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Skype for Business での Exchange ユニファイド メッセージング統合の計画

**の概要:** ビジネスのサーバーで Exchange 2013 または 2016 の Skype を統合するために計画するときに、このトピックを確認します。

ビジネス サーバーの Skype では、ボイス メッセージングと電子メールのメッセージを単一のメッセージング インフラストラクチャを組み合わせる場合の Exchange ユニファイド メッセージング (UM) との統合をサポートしています。 Exchange では、Exchange ユニファイド メッセージング (UM) をインストールして構成することができますいくつかの Exchange サーバーの役割の 1 つです。

2016 と Microsoft Exchange Server 2013 は、Exchange UM サービスとして実行 Exchange メールボックス サーバーにします。 ビジネス サーバーのエンタープライズ VoIP 展開の Skype では、ユニファイド メッセージング、ボイス メッセージングと電子メール メッセージングをユーザーが電話 (Outlook Voice Access) またはコンピューターからアクセスできる 1 つのストアが組み合わせたものです。 ユニファイド メッセージングと Skype ビジネス サーバーのエンタープライズ VoIP のユーザーが通話応答、Outlook Voice Access、および自動応答サービスを提供するために連携します。

> [!NOTE]
> Exchange UM のまま Skype で利用可能なビジネス サーバー 2019 の Exchange 2013 または Exchange 2016 2019 のビジネス用の Skype を統合する場合です。 2019 の Exchange でのサポートの変更により、Exchange UM の統合は、ボイスメールのクラウドとクラウドの自動応答の機能のための emphasised ことです。  詳細については、[クラウドのボイスメールの計画サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)と[Skype ビジネス サーバーと Exchange Server の移行のための計画](../../../sfbhybrid/hybrid/plan-um-migration.md)を参照してください。


設置型 Exchange UM の展開でサポートされているこれらの機能では、する必要があります実行されている次のいずれか。

- Microsoft Exchange Server 2010 または最新の service pack (Skype ビジネス サーバーの 2015 のみの)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (Skype ビジネス サーバー 2019 のみ)

> [!NOTE]
> ユニファイド メッセージングと呼ばれていたになって Skype ビジネス サーバー 2019 は、電話システムを使用して、ボイスメールのメッセージを記録し、ユーザーの Exchange メールボックスに記録を残すのために使用できます。 詳細については、[クラウドのボイスメールの計画サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)を参照してください。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>統合されたユニファイド メッセージングと Skype ビジネス サーバー用の機能

ビジネス サーバー、エンタープライズ VoIP の Skype では、通話応答、通話の通知、音声アクセス (ボイス ・ メールを含む)、および自動応答サービスを提供するのに Exchange ユニファイド メッセージング (UM) インフラストラクチャを使用します。

- **通話応答** 通話応答は、ユーザーが電話に出られないときや通話が取り込み中のときに、ユーザーに代わって音声メッセージを受け取る機能です。個人用の応答メッセージの再生と、メッセージの録音ができます。メッセージはキューに登録され、ユーザーのメールボックスに配信されます。ユーザーのメールボックスは、Exchange メールボックス サーバーに格納されています。

    発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。

- **Outlook Voice Access**Outlook Voice Access には、ボイス ・ メールだけでなく、できるだけでなく、電子メール、予定表、およびテレフォニー インターフェイスから連絡先を含む、Exchange 受信トレイにアクセスするのには、エンタープライズ VoIP ユーザーが有効にします。 サブスクライバー アクセス番号は、Exchange UM 管理者によって割り当てられます。

- **自動アテンダント**自動アテンダントは、外部ユーザーの会社の代表者に到達するためにダイアルする電話番号を構成に使用できる Exchange UM 機能です。 具体的には、一連のメニュー システム内を移動する、外部の呼び出し元を支援する音声案内が用意されています。 Exchange UM 管理者が Exchange UM サーバーで使用可能なオプションの一覧を構成するとします。

- **Fax サービス**Exchange UM fax 機能には、Exchange のメールボックスで fax を受信するユーザーを有効にするが含まれています。 詳細については、Microsoft Exchange Server のマニュアルで[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?linkId=135652)を参照してください。

    > [!NOTE]
    > Exchange UM サーバーが提供する fax サービスは、ビジネスのサーバー展開では Microsoft Exchange Server 2010、最新のサービス パックと Exchange 2010、Exchange 2013、または Exchange 2016 と統合されている Skype でご利用いただけません。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>コンポーネントおよび設置が Skype のビジネス サーバーでユニファイド メッセージングのトポロジ

### <a name="exchange-server-components"></a>Exchange Server コンポーネント

Exchange UM の機能とエンタープライズ VoIP ユーザーが組織内に[統合されたユニファイド メッセージングと Skype ビジネス サーバー用の機能](#features-of-integrated-unified-messaging-and-skype-for-business-server)で説明したサービスを提供するには、Microsoft Exchange メールボックス サーバーとクライアント アクセスを展開する必要があります。サーバー、ユーザーのメールボックスをホストし、電子メール、ボイス メールを 1 つのストレージの場所を提供します。 Exchange UM Exchange のメールボックスおよびクライアント アクセス サーバーでサービスとして実行されます。

詳細については、Microsoft Exchange Server 2010 での Exchange UM コンポーネントは、[展開する設置型 Exchange UM Lync Server 2013 プレビュー音声メールの提供を](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)参照してください。

### <a name="supported-topologies"></a>サポートされているトポロジ

ビジネス サーバーおよび Exchange ユニファイド メッセージング (UM) 同じフォレスト内または複数のフォレストでの Skype を展開できます。 展開では、複数のフォレストをまたがっている場合は、各 Exchange UM フォレストの Exchange 統合の手順を行う必要があります。 さらに、各 Exchange UM フォレストを信頼するには、Business Server フォレストの Skype と Business Server フォレストの Skype を信頼する場合は、各 Microsoft Exchange フォレストを構成する必要があります。 このフォレストの信頼の他には、Business Server フォレストの Skype では、ユーザー オブジェクトのすべてのユーザーの Exchange UM の設定を設定しなければなりません。

ビジネス サーバーの Skype では、Exchange UM の統合のため次のトポロジがサポートされています。

- 単一フォレスト

- 1 つのドメイン (つまり、1 つのドメインの単一フォレスト)。 ビジネス サーバー、Microsoft Exchange、およびユーザーの Skype は、同じドメインに存在します。

- 複数ドメイン (つまり、1 つまたは複数の子ドメインとルート ドメイン)。 Skype ビジネス サーバー、および Microsoft Exchange サーバーは、ユーザーを作成するドメインから別のドメインに配置されます。 ビジネス サーバー プールをサポートしているため、Skype から別のドメインでは、Exchange UM サーバーを展開できます。

- 複数のフォレスト (リソース フォレストとは、)。 Skype ビジネス サーバーの単一のフォレストに展開し、複数のフォレストにユーザーが分散し、します。 ユーザーの Exchange UM の属性は、Business Server フォレストの Skype を経由でレプリケートする必要があります。

    > [!NOTE]
    > Exchange は、複数のフォレストに展開できます。 各 Exchange 組織が提供できる Exchange UM に、ユーザー、または Exchange UM ビジネス サーバーの Skype と同じフォレストに展開することができます。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>統合するためのガイドラインの設置型ユニファイド メッセージングおよび Skype ビジネス サーバーの

ガイドラインとエンタープライズ VoIP を展開する際に考慮すべきベスト プラクティスを次に示します。

> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) UCMA 4 を使用する場合にのみ、IPv6 をサポートします。

- Skype のビジネス サーバーの Standard Edition サーバーまたはフロント エンド プールを展開します。

- タスクごとのしたことを確認するのには Exchange 管理者の作業は、成功、スムーズな統合を保証するために実行されます。

- Exchange UM のユーザーを有効にする各 Exchange ユニファイド メッセージング (UM) フォレスト内の Exchange メールボックス サーバーの役割を展開します。 Exchange サーバーの役割のインストール方法の詳細については、Microsoft Exchange Server 2013 のマニュアルを参照してください。

    > [!IMPORTANT]
    > Exchange ユニファイド メッセージング (UM) がインストールされている場合、自己署名証明書を使用するように構成されます。 自己署名入りの証明書は、Skype ビジネス サーバーと Exchange UM、互いに信頼されるため、両方のサーバーを信頼する証明機関から個別の証明書を要求する必要があるを有効にできません。

- ビジネス サーバーおよび Exchange UM の Skype は別々 のフォレストにインストールする場合は、各 Exchange フォレストを信頼するには、Business Server フォレストの Skype と Business Server フォレストの Skype を信頼するには、各 Exchange フォレストを構成します。 また、セットは、ユーザーの Exchange UM の設定 Business Server フォレストの場合は、Skype では、ユーザー オブジェクトの通常スクリプトまたはフォレスト間のツールでは、アイデンティティのライフ サイクル マネージャー (ILM) などを使用しています。

- 必要に応じて、ユニファイド メッセージング サーバーを管理する Exchange 管理コンソールをインストールします。

- Outlook Voice Access と自動応答の有効な電話番号を取得します。

- Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合、Exchange UM SIP の URI に対して座標の名前は、計画およびエンタープライズ VoIP のダイヤル プランをダイヤルします。

### <a name="deploying-redundant-exchange-um-servers"></a>冗長 Exchange UM サーバーを展開します。

> [!IMPORTANT]
> どの Exchange UM サービスが実行されて、組織用に構成する各 Exchange UM ・ SIP ・ URI ダイヤル プランの 2 つのサーバーの最小値を配置することをお勧めします。 拡張された容量を提供し、冗長化されたサーバーを展開する高可用性を提供します。 サーバー障害時に、別のサーバーにフェールオーバーする Skype のビジネス サーバーを構成できます。

次の例の構成では、Exchange UM の弾力性を提供します。

**例 1: Exchange UM の弾力性**

![Exchange UM の復元性の図](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

例 1 の場合は、タクウィラに設置されて、データ ・ センターの 1 と 2 の Exchange UM サーバーが有効になっているし、ダブリン データ センターに Exchange UM サーバー 3 と 4 が有効になっています。 Exchange UM システム停止の際に、タクウィラに設置されて、サーバーを指す 3 と 4 をそれぞれ 1 と 2 のサーバーのドメイン ネーム システム (DNS) A レコードを構成してください。 Exchange UM システム停止の際に、ダブリン、サーバーを指す 1 と 2、それぞれ 3 と 4 のサーバーの DNS の A レコードを構成してください。

> [!NOTE]
> 例 1 を割り当てる必要がありますも各 UM サーバーに証明書を次のいずれか: 証明書をサブジェクト代替名 (SAN) でワイルドカードを使用するか、4 つ Exchange UM サーバー、SAN 内のそれぞれの完全修飾ドメイン名 (FQDN) を配置します。

**例 2: Exchange UM の弾力性**

![Exchange UM の復元性の図](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

例 2 では、通常の運用条件下でタクウィラに設置されて、データ ・ センターの 1 と 2 の Exchange UM サーバーが有効になっているし、ダブリン データ センターに Exchange UM サーバー 3 と 4 が有効になっています。 タクウィラに設置されてユーザーの SIP URI ダイヤル プランは 4 つのすべてのサーバーが含まれますただし、サーバー 3 と 4 は無効です。 などの障害発生時に、Exchange UM でタクウィラに設置されて、1 と 2 の Exchange UM サーバーを無効にする必要がありますおよびタクウィラに設置されて Exchange UM トラフィックはダブリンにあるサーバーにルーティングされるため、Exchange UM サーバー 3 と 4 を有効にする必要があります。

有効にするか、Exchange 2013 のユニファイド メッセージングを無効にする方法の詳細については、[統合 Exchange 2013 UM Lync Server を](https://go.microsoft.com/fwlink/p/?LinkId=265372)参照してください。 提供された情報に等しく適用されます Skype ビジネス サーバーにします。

有効にするか、Microsoft Exchange Server 2010 のユニファイド メッセージングを無効にする方法の詳細については、次のように表示されます。

- [Exchange 2010 でユニファイド メッセージングを有効にします。](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Exchange 2010 でユニファイド メッセージングを無効にします。](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange ユニファイド メッセージングが聞こえなくなった Exchange 2019、Exchange 2019 があり、[計画クラウド ボイスメール サービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)に記載されているクラウドのボイスメール サービスを使用する必要がありますが同等の機能を使用する場合。


## <a name="see-also"></a>関連項目

[オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要](deployment-overview.md)
