---
title: Skype for Business での Exchange ユニファイド メッセージング統合の計画
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
description: '概要: は、Exchange 2013 でのビジネス サーバー 2015 の Skype を統合するために計画するときにこのトピックを参照します。'
ms.openlocfilehash: 1a1ea968f9feb14c0a7b0d69c13ad273a18a53f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-exchange-unified-messaging-integration-in-skype-for-business"></a>Skype for Business での Exchange ユニファイド メッセージング統合の計画
 
**の概要:**Exchange 2013 でのビジネス サーバー 2015 の Skype を統合するために計画するときに、このトピックを確認します。
  
ビジネス サーバー 2015 の Skype では、ボイス メッセージングと電子メールのメッセージを単一のメッセージング インフラストラクチャを組み合わせる場合の Exchange ユニファイド メッセージング (UM) との統合をサポートしています。 Exchange では、Exchange ユニファイド メッセージング (UM) をインストールして構成することができますいくつかの Exchange サーバーの役割の 1 つです。 
  
Microsoft Exchange Server 2013 で Exchange UM サービスとして実行 Exchange メールボックス サーバーにします。 ビジネス サーバー 2015 のエンタープライズ VoIP 展開の Skype では、ユニファイド メッセージング、ボイス メッセージングと電子メール メッセージングをユーザーが電話 (Outlook Voice Access) またはコンピューターからアクセスできる 1 つのストアが組み合わせたものです。 ユニファイド メッセージングおよびビジネス サーバー 2015 の Skype は連携して、エンタープライズ VoIP のユーザーが通話応答、Outlook Voice Access、および自動応答サービスを提供します。
  
Microsoft Exchange Server 2013 のアーキテクチャの変更の詳細については、Microsoft Exchange Server 2013 のドキュメントでの[ボイスのアーキテクチャの変更](https://go.microsoft.com/fwlink/p/?LinkId=266730)を参照してください。
  
設置型 Exchange UM の展開でサポートされているこれらの機能では、する必要があります実行されている次のいずれか。
  
- Microsoft Exchange Server 2010 または最新の service pack
    
- Microsoft Exchange Server 2013
    
-  Microsoft Exchange Server 2016
    
## <a name="features-of-integrated-unified-messaging-and-skype-for-business-server-2015"></a>統合ユニファイド メッセージングと Skype for Business Server 2015 の機能

ビジネス サーバー 2015、エンタープライズ VoIP の Skype では、通話応答、通話の通知、音声アクセス (ボイス ・ メールを含む)、および自動応答サービスを提供するのに Exchange ユニファイド メッセージング (UM) インフラストラクチャを使用します。
  
- **通話応答** 通話応答は、ユーザーが電話に出られないときや通話が取り込み中のときに、ユーザーに代わって音声メッセージを受け取る機能です。個人用の応答メッセージの再生と、メッセージの録音ができます。メッセージはキューに登録され、ユーザーのメールボックスに配信されます。ユーザーのメールボックスは、Exchange メールボックス サーバーに格納されています。
    
    発信者がメッセージを残すと、ユーザーの受信トレイにメッセージがルーティングされます。発信者がメッセージを残さなかった場合は、不在着信通知がユーザーのメールボックスに格納されます。 ユーザーが自分の受信トレイにアクセスするには、Microsoft Outlook のメッセージングおよびコラボレーション クライアント、Outlook Web Access、Exchange ActiveSync テクノロジ、または Outlook Voice Access を使用します。 電子メールと同様の方法で、着信の件名と優先度を表示できます。
    
- **Outlook Voice Access**Outlook Voice Access には、ボイス ・ メールだけでなく、できるだけでなく、電子メール、予定表、およびテレフォニー インターフェイスから連絡先を含む、Exchange 受信トレイにアクセスするのには、エンタープライズ VoIP ユーザーが有効にします。 サブスクライバー アクセス番号は、Exchange UM 管理者によって割り当てられます。
    
- **自動アテンダント**自動アテンダントは、外部ユーザーの会社の代表者に到達するためにダイアルする電話番号を構成に使用できる Exchange UM 機能です。 具体的には、一連のメニュー システム内を移動する、外部の呼び出し元を支援する音声案内が用意されています。 Exchange UM 管理者が Exchange UM サーバーで使用可能なオプションの一覧を構成するとします。
    
- **Fax サービス**Exchange UM fax 機能には、Exchange のメールボックスで fax を受信するユーザーを有効にするが含まれています。 詳細については、Microsoft Exchange Server のマニュアルで[ユニファイド メッセージング](https://go.microsoft.com/fwlink/p/?linkId=135652)を参照してください。
    
    > [!NOTE]
    > Exchange UM サーバーが提供する fax サービスは、ビジネスのサーバー展開では Microsoft Exchange Server 2010、最新サービス パックを使用する Exchange 2010 または Exchange 2013 に統合されている Skype でご利用いただけません。 
  
## <a name="components-and-topologies-for-on-premises-unified-messaging-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 のオンプレミスのユニファイド メッセージングのコンポーネントとトポロジ

### <a name="exchange-server-components"></a>Exchange Server コンポーネント

Exchange UM の機能と[機能の統合されたユニファイド メッセージングおよび Lync Server 2013](http://technet.microsoft.com/library/094f549d-fccc-43ab-9f39-6ddd18130915.aspx)の「組織のエンタープライズ VoIP ユーザーにサービスを提供する、Microsoft Exchange メールボックス サーバーとクライアント アクセス サーバーを配置する必要があります。ユーザーのメールボックスをホストし、メールやボイス ・ メールの 1 つのストレージの場所を提供します。 Exchange UM Exchange のメールボックスおよびクライアント アクセス サーバーでサービスとして実行されます。
  
Microsoft Exchange Server 2010 での Exchange UM コンポーネントに関する詳細については、展開に関するドキュメントに[配置する設置型 Exchange UM Lync Server 2013 プレビュー音声メールの提供を](http://technet.microsoft.com/library/9673bd73-a3a3-425d-870f-04d801c6d0d5.aspx)参照してください。
  
### <a name="supported-topologies"></a>サポートされるトポロジ

ビジネス サーバー 2015 および Exchange ユニファイド メッセージング (UM) 同じフォレスト内または複数のフォレストでの Skype を展開できます。 展開では、複数のフォレストをまたがっている場合は、各 Exchange UM フォレストの Exchange 統合の手順を行う必要があります。 さらに、各 Exchange UM フォレストを信頼するフォレストのビジネス サーバー 2015 Skype とビジネス サーバー 2015 フォレストの Skype を信頼する場合は、各 Microsoft Exchange フォレストを構成する必要があります。 このフォレストの信頼だけでなく、Skype のビジネス サーバー 2015 フォレストでユーザー オブジェクトのすべてのユーザーの Exchange UM の設定を設定しなければなりません。 
  
ビジネス サーバー 2015 の Skype には、Exchange UM の統合のための次のトポロジがサポートされています。
  
- 単一のフォレスト
    
- 単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。 ビジネス サーバー 2015、Microsoft Exchange、およびユーザーの Skype は、同じドメインに存在します。
    
- 複数ドメイン (つまり、1 つまたは複数の子ドメインとルート ドメイン)。 Skype ビジネス サーバー 2015 年と Microsoft Exchange サーバーは、ユーザーを作成するドメインから別のドメインに配置されます。 Exchange UM サーバーは、Skype をサポートしているビジネス サーバー 2015 プールから別のドメインに展開できます。
    
- 複数のフォレスト (すなわち、リソース フォレスト)。 ビジネス サーバー 2015 の Skype は、単一のフォレストに展開し、複数のフォレストにユーザーが分散し、します。 ユーザーの Exchange UM の属性は、ビジネス サーバー 2015 フォレストの Skype を経由でレプリケートする必要があります。
    
    > [!NOTE]
    > Exchange は複数のフォレストに展開できます。 各 Exchange 組織が提供できる Exchange UM に、ユーザー、または Exchange UM ビジネス サーバー 2015 の Skype と同じフォレストに展開することができます。 
  
## <a name="guidelines-for-integrating-on-premises-unified-messaging-and-skype-for-business-server-2015"></a>オンプレミスのユニファイド メッセージングと Skype for Business Server 2015 を統合するためのガイドライン

次に示すのは、エンタープライズ VoIP の展開時に考慮すべきガイドラインおよびベスト プラクティスです。
  
> [!IMPORTANT]
> Exchange ユニファイド メッセージング (UM) UCMA 4 を使用する場合にのみ、IPv6 をサポートします。 
  
- Skype のビジネス サーバー 2015 の Standard Edition サーバーまたはフロント エンド プールを展開します。 インストールに関する詳細については、展開に関するドキュメントで[ビジネス サーバー 2015 の Skype の導入](../../deploy/deploy.md)を参照してください。
    
- スムーズに問題なく統合できるように、Exchange 管理者と協力して、各自が実施する作業を確認します。
    
- Exchange UM のユーザーを有効にする各 Exchange ユニファイド メッセージング (UM) フォレスト内の Exchange メールボックス サーバーの役割を展開します。 Exchange サーバーの役割のインストール方法の詳細については、Microsoft Exchange Server 2013 のマニュアルを参照してください。
    
    > [!IMPORTANT]
    > Exchange ユニファイド メッセージング (UM) がインストールされている場合、自己署名証明書を使用するように構成されます。 自己署名入りの証明書は、Skype ビジネス サーバー 2015 と Exchange UM、互いに信頼されるため、両方のサーバーを信頼する証明機関から個別の証明書を要求する必要があるを有効にできません。 
  
- ビジネス サーバー 2015 と Exchange UM の Skype は別々 のフォレストにインストールする場合は、各 Exchange フォレストを信頼するフォレストのビジネス サーバー 2015 Skype およびビジネス サーバー 2015 フォレストの Skype を信頼するには、各 Exchange フォレストを構成します。 また、セットは、ユーザーの Exchange UM の設定ビジネス サーバー 2015 フォレストの場合は、Skype では、ユーザー オブジェクトの通常スクリプトまたはフォレスト間のツールでは、アイデンティティのライフ サイクル マネージャー (ILM) などを使用しています。
    
- 必要に応じて、ユニファイド メッセージング サーバーを管理するのに Exchange 管理コンソールをインストールします。
    
- Outlook Voice Access および自動応答の有効な電話番号を取得します。
    
- Microsoft Exchange Server 2010 Service Pack 1 (SP1) より前のバージョンの Exchange UM を使用している場合、Exchange UM SIP の URI に対して座標の名前は、計画およびエンタープライズ VoIP のダイヤル プランをダイヤルします。 
    
### <a name="deploying-redundant-exchange-um-servers"></a>冗長 Exchange UM サーバーの展開

> [!IMPORTANT]
> どの Exchange UM サービスが実行されて、組織用に構成する各 Exchange UM ・ SIP ・ URI ダイヤル プランの 2 つのサーバーの最小値を配置することをお勧めします。 拡張された処理能力を提供することに加えて、冗長サーバーを展開することは高可用性を提供します。 サーバーに障害が発生した場合は、別のサーバーにフェールオーバーするビジネス サーバー 2015 の Skype を構成できます。 
  
次に示すのは、Exchange UM の復元性を提供する構成例です。
  
**例 1: Exchange UM の弾力性**

![Exchange UM の復元性の図](../../media/d8381ecc-0e4e-47ea-9bf7-e54fec9414e7.png)
  
例 1 では、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。Tukwila で Exchange UM サーバーが停止した場合、サーバー 1 と 2 のドメイン ネーム システム (DNS) A レコードを、サーバー 3 と 4 それぞれに向くよう、構成します。Dublin で Exchange UM サーバーが停止した場合、サーバー 3 と 4 の DNS A レコードを、サーバー 1 と 2 それぞれに向くよう、構成します。
  
> [!NOTE]
> 例 1 を割り当てる必要がありますも各 UM サーバーに証明書を次のいずれか: 証明書をサブジェクト代替名 (SAN) でワイルドカードを使用するか、4 つ Exchange UM サーバー、SAN 内のそれぞれの完全修飾ドメイン名 (FQDN) を配置します。 
  
**例 2: Exchange UM の弾力性**

![Exchange UM の復元性の図](../../media/4ad101c3-f318-4fc0-b4da-c05f2e92a943.png)
  
例 2 では、通常の操作条件の下、Exchange UM サーバー 1 と 2 は Tukwila のデータ センターで有効化されています。Exchange UM サーバー 3 と 4 は Dublin のデータ センターで有効化されています。4 台すべてのサーバーが Tukwila のユーザーの SIP URL ダイヤル プランに含まれていますが、サーバー 3 と 4 は有効化されていません。たとえば、Tukwila で Exchange UM サーバーが停止した場合、Exchange UM サーバー 1 と 2 は無効化され、Tukwila の Exchange UM トラフィックが Dublin のサーバーにルーティングされるよう、Exchange UM サーバー 3 と 4 は有効化されます。
  
有効にするか、Exchange 2013 のユニファイド メッセージングを無効にする方法の詳細については、[統合 Exchange 2013 UM Lync Server を](https://go.microsoft.com/fwlink/p/?LinkId=265372)参照してください。 提供された情報に等しく適用されます Skype ビジネス サーバー 2015 のです。
  
有効にするか、Microsoft Exchange Server 2010 のユニファイド メッセージングを無効にする方法の詳細については、次のように表示されます。
  
- [Exchange 2010 でユニファイド メッセージングを有効にします。](https://go.microsoft.com/fwlink/p/?LinkId=204418)
    
- [Exchange 2010 でユニファイド メッセージングを無効にします。](https://go.microsoft.com/fwlink/p/?LinkId=204416)
    
## <a name="see-also"></a>関連項目

#### 

[統合するための展開プロセスの概要、設置型ユニファイド メッセージングおよびビジネス用の Skype](deployment-overview.md)

