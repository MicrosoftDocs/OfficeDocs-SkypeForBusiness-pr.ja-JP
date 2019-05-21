---
title: Skype for Business での Exchange ユニファイド メッセージング統合の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7b22002b-7e6a-4d3f-b600-a733a7e3778a
description: '概要: Skype for Business Server を Exchange 2013 または2016に統合する計画中に、このトピックを確認してください。'
ms.openlocfilehash: 3b71dd740440aeab37919bb94ef98eaeb83d4d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297345"
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Skype for Business での Exchange ユニファイド メッセージング統合の計画

**概要:** Skype for Business Server を Exchange 2013 または2016に統合する計画中に、このトピックを確認してください。

Skype for Business Server は、音声メッセージとメールメッセージを1つのメッセージングインフラストラクチャに統合するための Exchange ユニファイドメッセージング (UM) との統合をサポートしています。 Exchange の exchange ユニファイドメッセージング (UM) は、インストールして構成できる Exchange server の役割の1つです。

Microsoft Exchange Server 2013 および2016では、exchange UM は Exchange メールボックスサーバー上のサービスとして実行されます。 Skype for Business Server エンタープライズ Voip 展開の場合、ユニファイドメッセージングは、音声メッセージとメールメッセージを1つのストアにまとめて、ユーザーが電話 (Outlook Voice Access) またはコンピューターからアクセスできるようにします。 ユニファイドメッセージングと Skype for Business Server が連携して、エンタープライズ Voip のユーザーへの通話応答、Outlook Voice Access、自動応答サービスを提供します。

> [!NOTE]
> Skype for business 2019 を Exchange 2013 または Exchange 2016 と統合すると、exchange UM は Skype for Business Server 2019 で利用可能になります。 Exchange 2019 のサポートが変更されたため、クラウドボイスメールとクラウド自動応答機能を利用して、Exchange UM との統合を強調することができます。  詳細については、「[クラウドボイスメールサービスの計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」および「 [Skype for Business Server と Exchange server の移行の計画](../../../sfbhybrid/hybrid/plan-um-migration.md)」を参照してください。


オンプレミスの Exchange UM 展開でこれらの機能をサポートするには、次のいずれかを実行している必要があります。

- Microsoft Exchange Server 2010 または最新の service pack (Skype for Business Server 2015 のみ)
- Microsoft Exchange Server 2013
- Microsoft Exchange Server 2016
- Microsoft Exchange Server 2019 (Skype for Business Server 2019 のみ)

> [!NOTE]
> 以前に認識されていた Exchange ユニファイドメッセージングは、Skype for Business Server 2019 では利用できなくなりました。電話システムを使用してボイスメールメッセージを記録し、ユーザーの Exchange メールボックスに記録したままにします。 詳細については、「[クラウドボイスメールサービスの計画](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」を参照してください。

## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server"></a>統合されたユニファイドメッセージングと Skype for Business Server の機能

Skype for Business Server のエンタープライズボイスは、Exchange ユニファイドメッセージング (UM) インフラストラクチャを使用して、通話応答、通話通知、音声アクセス (ボイスメールを含む)、自動応答サービスを提供します。

- **通話応答** 通話応答は、ユーザーが電話に出られないときや通話が取り込み中のときに、ユーザーに代わって音声メッセージを受け取る機能です。個人用の応答メッセージの再生と、メッセージの録音ができます。メッセージはキューに登録され、ユーザーのメールボックスに配信されます。ユーザーのメールボックスは、Exchange メールボックス サーバーに格納されています。

    発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。

- **Outlook Voice Access**Outlook Voice Access を使うと、エンタープライズボイスユーザーは、ボイスメールだけでなく、テレフォニーインターフェイスのメール、予定表、連絡先などの Exchange の受信トレイにもアクセスできます。 サブスクライバーのアクセス番号は、Exchange UM 管理者によって割り当てられます。

- **自動応答**自動応答は、外部のユーザーが会社の代表者に連絡するためにダイヤルできる電話番号を構成するために使用できる Exchange UM の機能です。 特に、外部の発信者によるメニューシステムの移動を支援する一連の音声プロンプトが用意されています。 使用できるオプションの一覧は、exchange um 管理者によって Exchange UM サーバー上で構成されます。

- **Fax サービス**Exchange UM には fax 機能が含まれています。これにより、ユーザーは Exchange メールボックスで着信 fax を受信できるようになります。 詳細については、Microsoft Exchange Server ドキュメントの「[ユニファイドメッセージング](https://go.microsoft.com/fwlink/p/?linkId=135652)」を参照してください。

    > [!NOTE]
    > Exchange UM サーバーによって提供される Fax サービスは、Microsoft exchange server 2010 2010 に統合されている Skype for business server の展開、および最新の service pack、exchange 2013、または exchange 2016 では利用できません。

## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server"></a>Skype for Business Server のオンプレミスユニファイドメッセージングのコンポーネントとトポロジ

### <a name="exchange-server-components"></a>Exchange Server コンポーネント

統合された[ユニファイドメッセージングおよび Skype For Business Server の機能](#features-of-integrated-unified-messaging-and-skype-for-business-server)で説明されている Exchange UM の機能とサービスを組織内のエンタープライズボイスユーザーに提供するには、Microsoft Exchange メールボックスサーバーとクライアントアクセスを展開する必要があります。サーバー。ユーザーメールボックスをホストし、メールやボイスメール用の1つの保存場所を提供します。 Exchange UM は、Exchange メールボックスとクライアントアクセスサーバーでサービスとして実行されます。

Microsoft Exchange Server 2010 の Exchange UM コンポーネントの詳細については、「[オンプレミスの EXCHANGE um を展開して Lync Server 2013 のボイスメールを提供する](https://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)」を参照してください。

### <a name="supported-topologies"></a>サポートされるトポロジ

同じフォレストまたは複数のフォレストに、Skype for Business Server と Exchange ユニファイドメッセージング (UM) を展開することができます。 展開が複数のフォレストにまたがる場合は、各 Exchange UM フォレストの Exchange 統合手順を実行する必要があります。 さらに、Skype for Business Server フォレストと Skype for Business Server フォレストがそれぞれの Exchange UM フォレストを信頼するように Microsoft Exchange フォレストを設定する必要があります。 このフォレストの信頼に加えて、Skype for Business Server フォレストのユーザーオブジェクトに対して、すべてのユーザーの Exchange UM 設定を設定する必要があります。

Skype for Business Server は、Exchange UM との統合のために次のトポロジをサポートしています。

- 1つのフォレスト

- 単一ドメイン (つまり、単一のドメインを持つ単一フォレスト)。 Skype for Business Server、Microsoft Exchange、およびユーザーはすべて同じドメインに存在します。

- 複数のドメイン (つまり、1つ以上の子ドメインを持つルートドメイン)。 Skype for Business Server と Microsoft Exchange サーバーは、ユーザーを作成するドメインとは異なるドメインに展開されます。 Exchange UM サーバーは、サポートされている Skype for Business サーバープールのさまざまなドメインに展開できます。

- 複数のフォレスト (リソースフォレスト)。 Skype for Business Server は1つのフォレストに展開され、ユーザーは複数のフォレストに分散されます。 ユーザーの Exchange UM 属性は、Skype for Business Server フォレストにレプリケートする必要があります。

    > [!NOTE]
    > Exchange は複数のフォレストに展開できます。 各 Exchange 組織では、Exchange UM をユーザーに提供できます。また、Exchange UM は、Skype for Business Server と同じフォレストに展開できます。

## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server"></a>オンプレミスユニファイドメッセージングと Skype for Business Server を統合するためのガイドライン

エンタープライズ Voip を展開する際のガイドラインとベストプラクティスを次に示します。

> [!IMPORTANT]
> Exchange ユニファイドメッセージング (UM) は、UCMA 4 も使用している場合にのみ、IPv6 をサポートします。

- Skype for Business Server Standard Edition サーバーまたはフロントエンドプールを展開します。

- Exchange 管理者と協力して、どのタスクが実行されるかを確認して、円滑かつ確実に統合されるようにします。

- Exchange UM のユーザーを有効にする exchange の各ユニファイドメッセージング (UM) フォレストに Exchange メールボックスサーバーの役割を展開します。 Exchange server の役割のインストールの詳細については、Microsoft Exchange Server 2013 に関するドキュメントを参照してください。

    > [!IMPORTANT]
    > Exchange ユニファイドメッセージング (UM) がインストールされている場合は、自己署名証明書を使用するように構成されています。 自己署名証明書では、Skype for Business Server と Exchange UM が相互に信頼することはできません。このため、両方のサーバーが信頼する証明機関の証明書を個別に要求する必要があります。

- Skype for Business Server と Exchange UM が異なるフォレストにインストールされている場合は、各 Exchange フォレストが Skype for Business Server フォレストと Skype for Business Server フォレストを信頼するように構成して、各 Exchange フォレストを信頼するようにします。 また、ユーザーの Exchange UM 設定を Skype for Business Server フォレスト内のユーザーオブジェクトに対して設定します。通常は、スクリプトまたは Id ライフサイクルマネージャー (ILM) などのフォレスト間ツールを使用します。

- 必要に応じて、Exchange 管理コンソールをインストールしてユニファイドメッセージングサーバーを管理します。

- Outlook Voice Access および自動応答の有効な電話番号を取得します。

- Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合は、Exchange UM SIP URI ダイヤルプランとエンタープライズボイスダイヤルプランの名前を調整します。

### <a name="deploying-redundant-exchange-um-servers"></a>冗長な Exchange UM サーバーの展開

> [!IMPORTANT]
> 組織に対して構成した各 Exchange UM SIP URI ダイヤルプランについて、Exchange UM サービスが実行されている最低2台のサーバーを展開することをお勧めします。 拡張された容量の提供に加えて、冗長サーバーの展開によって可用性が高まります。 サーバーに障害が発生した場合、Skype for Business Server を別のサーバーにフェールオーバーするように構成することができます。

次に示す構成の例では、Exchange UM の回復性が提供されています。

**例 1: Exchange UM の回復性**

![Exchange UM の復元性の図](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)

例1では、Exchange UM サーバー1と2が、データセンターで有効になっています。また、Exchange UM サーバー3と4は、ダブリンデータセンターで有効になっています。 Tua で Exchange UM が停止した場合、サーバー1と2のドメインネームシステム (DNS) A レコードは、それぞれサーバー3と4をポイントするように構成する必要があります。 Dublin で Exchange UM が停止した場合は、サーバー3および4の DNS A レコードをそれぞれサーバー1と2にポイントするように構成する必要があります。

> [!NOTE]
> たとえば1の場合、各 Exchange UM サーバーに次のいずれかの証明書を割り当てる必要があります。 [サブジェクト代替名] にワイルドカードを使用するか、または SAN 内の4つの Exchange UM サーバーの完全修飾ドメイン名 (FQDN) を入力します。

**例 2: Exchange UM の回復性**

![Exchange UM の復元性の図](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)

例2の [通常の運用条件] では、データセンターでの Exchange UM サーバー1と2が有効になっています。また、Exchange UM サーバー3と4は、ダブリンデータセンターで有効になっています。 この4つのサーバーはすべて、ユーザーの SIP URI ダイヤルプランに含まれています。ただし、サーバー3と4は無効です。 Tukwila Exchange UM が停止した場合は、Exchange um サーバー1と2を無効にして、exchange UM サーバー3と4を有効にする必要があります。これにより、exchange um トラフィックが Dublin のサーバーにルーティングされるようになります。

Exchange 2013 でユニファイドメッセージングを有効または無効にする方法の詳細については、「 [exchange 2013 UM と Lync Server を統合](https://go.microsoft.com/fwlink/p/?LinkId=265372)する」を参照してください。 提供されている情報は、Skype for Business Server に同様に適用されます。

Microsoft Exchange Server 2010 でユニファイドメッセージングを有効または無効にする方法の詳細については、以下を参照してください。

- [Exchange 2010 でユニファイドメッセージングを有効にする](https://go.microsoft.com/fwlink/p/?LinkId=204418)

- [Exchange 2010 でユニファイドメッセージングを無効にする](https://go.microsoft.com/fwlink/p/?LinkId=204416)

### <a name="exchange-server-2019"></a>Exchange Server 2019

Exchange のユニファイドメッセージングは Exchange 2019 に存在しなくなりました。 Exchange 2019 を使用していて、同等の機能が必要な場合は、「[プランクラウドボイスメールサービス](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md)」で説明されているクラウドボイスメールサービスを使用する必要があります。


## <a name="see-also"></a>関連項目

[オンプレミス ユニファイド メッセージングと Skype for Business を統合するための展開プロセスの概要](deployment-overview.md)
