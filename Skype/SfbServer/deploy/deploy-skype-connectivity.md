---
title: Skype for business Server での Skype 接続の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: skype for business Server を Skype コンシューマーと接続する方法について説明します。 Skype 接続とも呼ばれます。'
ms.openlocfilehash: b0cae57ac357b2b88d74b6326176c7cb7cdaf22e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219747"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Skype for business Server での Skype 接続の展開

**概要:** Skype for business Server を Skype コンシューマーと接続する方法について説明します。 Skype 接続とも呼ばれます。
  
この記事では、Skype 接続の展開について順を追って説明します。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Connectivity の概要 (IT 担当者向け)

Skype Connectivity を使用すると、skype for Business ユーザーは、skype ユーザーを検索して追加することができます。 Skype Connectivity は、skype for business の機能です。これにより、Skype ユーザーとのフェデレーションとディレクトリ検索を有効にすることができます。 Skype 接続を有効にした後、skype for Business ユーザーは skype ユーザーを検索して追加できるようになります。
  
## <a name="skype-directory-search"></a>Skype ディレクトリ検索

Skype ディレクトリ検索機能を使用すると、skype for Business ユーザーは Skype 連絡先を検索することができます。 検索機能を使用すると、ユーザーは次のものを使用して検索できます。
  
- **表示名で検索し、"John Doe" の例**では、多くの結果が返される可能性があるため、探しているものが見つからない場合があります。
    
- 検索には、**表示名と場所を指定します。たとえば、"John Doe In Barcelona"** のようにします。これにより、検索結果を大幅に絞り込むことができます。
    
- **メールでの検索 (例: "johndoe@outlook.com"** )-これはほとんどの場合に1つの結果を返します。指定した電子メールに正確に一致するもの。 しかし、同じ電子メールが複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。
    
- **電話番号で検索します。例: "123-123-1234"** -これはほとんどの場合に1つの結果を返します。指定した電話に正確に一致するもの。 電話番号には国番号を含める必要があります (例: zzzz)。 同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。
    
- **Skype 名で検索します。例: "JohnDoe1456"** -完全一致が見つかった場合は、最初の結果として返されます。 その他の考えられる "名前" 一致が返される場合があります。
    
    > [!NOTE]
    > Skype ディレクトリ検索は、ポート443の次の IP アドレスと通信できる必要があります。104.40.75.246、23.101.135.34、および40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype ディレクトリ検索でサポートされている展開マトリックス

次の表は、Skype ディレクトリ検索のサポートの概要を示しています。
  

||**Skype for Business Server のフロントエンド**|**Lync Server 2013 (またはそれ以前) のフロントエンド**|**コメント**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |サポートされている  <br/> |サポート対象外  <br/> |Skype for business Server とエッジは、Skype ディレクトリ検索の前提条件です。  <br/> |
|Skype for Business Server Edge + Lync Server 2013 エッジ展開されたサイドバイサイド  <br/> |サポートされている  <br/> |サポート対象外  <br/> |Skype ディレクトリ検索トラフィックは、Skype for Business Server エッジサーバーを介してフローします。 フェデレーショントラフィックは、管理者によって構成されたエッジを経由します。 たとえば、管理者は、Skype ディレクトリ検索をサポートしていない Lync Server 2013 エッジサーバーを経由して、引き続きフェデレーショントラフィックを送信することを選択できます。  <br/> |
|Lync Server 2013 (またはそれ以前の) エッジ  <br/> |サポート対象外  <br/> |サポート対象外  <br/> ||
   
> [!NOTE]
> Addressbook service が Skype for Business Server のフロントエンドで実行されている場合、エッジサーバーの Skype Search ポート4443が存在するエッジを検索します。 
  
> [!NOTE]
> オンプレミス展開に複数のサイトがある顧客に対して、1つの Skype for Business Server エッジサーバーまたはプールのみを展開した場合、すべてのサイトからの検索トラフィックは、1つの使用可能なエッジサーバーを通過します。 管理者は、展開された Skype for Business Server エッジサーバーまたはプールにすべてのサイトからプールがアクセスできることを確認する必要があります。 
  
> [!NOTE]
> Skype graph サービスは、要求レートが15要求/秒を超えた場合に、オンプレミスまたは Microsoft 365 または Office 365 お客様からの検索要求を調整します。 
  
> [!NOTE]
> 大規模エンタープライズオンプレミスのお客様の場合は、要求速度の向上を可能にするために、ドメインを Skype search サービスでホワイトリストする必要があります。 
  
> [!NOTE]
> キューに保留中の要求が多すぎる場合、Skype for Business Server は着信要求を調整します。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Skype for business Online の Skype 接続の展開

Skype 接続は、Microsoft 365 および Office 365 の一部である Skype for Business Online の機能でもあります。 Skype Connectivity 機能は、Microsoft 365 管理センター内の Skype for Business 管理センターから有効にすることができます。
  
Microsoft 365 中規模企業、Office 365 Enterprise、Microsoft 365 エデュケーション、および Office 365 for Government: Microsoft 365 管理センターにサインインして、Skype for Business 管理センターに移動します。 [外部通信] に移動します。 [パブリック IM サービスプロバイダー] の下で、[有効にする] をクリックします。 個々のユーザーの Skype 接続へのアクセスを制御するには、個々のユーザーの外部通信設定を編集します。
  
Office 365 Small Business Premium の場合: Office 365 にサインインし、管理者 \> サービス設定の [ \> インスタントメッセージング]、[会議と会議] の順に移動します。 外部通信を有効にします。 外部通信スイッチは、skype for business を使用する他の組織との Skype 接続と通信の両方を有効にします。
  
Skype for Business Online の管理の詳細については、以下を参照してください。
  
- [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Skype for business または Skype の外部連絡先に IM できない場合の対処方法](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Skype for Business で連絡先を追加する](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理者向け: 個別のユーザーのために Skype for Business の設定を構成する](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Skype for business Server の Skype 接続の展開

Skype for Business Server は、フェデレーションアクセスアーキテクチャを使用して Skype との接続をサポートします。 この接続により、Skype for Business Server のユーザーは Skype を追加できるようになります。 Skype クライアントでは、Skype for Business ユーザーを連絡先リストに追加することもできます。 Skype for Business Server で管理上設定されたポリシーに基づいて、ユーザーはインスタントメッセージングを使用して通信したり、互いのプレゼンスを確認したり、音声およびビデオ通話を開始したりすることができます。 Skype 接続は、Skype for Business Online の機能でもあり、Microsoft 365 管理センター内の Skype for business 管理センターから、skype for business Online のお客様に対して有効にすることができます。
  
> [!NOTE]
> Skype for Business Server がパブリックインスタントメッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は既に Skype 接続用に構成されています。 検討する必要があるのは、既存の Messenger PIC エントリの名前を Skype に変更することだけです。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Server パブリック IM 接続プロビジョニングサイトが使用できなくなりました

以前は Skype for Business オンプレミス展開と Skype for business の間でフェデレーションを手動でプロビジョニングするために使用されていたサイトは必要なくなり、8/15/2019 にシャットダウンされます。 Skype とのフェデレーションでは、Skype for Business Online とのフェデレーションに必要なものと同じメカニズムであるフェデレーションパートナーの検出が利用されます。

既存のパブリック IM インフラストラクチャを使用したオンプレミスの Skype for Business 展開と Skype ユーザーの間の通信では、オンプレミスのエッジサーバー構成が Skype for Business Online と互換性を持つ必要があります。

> [!NOTE]
> ほとんどのお客様にとって必要な操作はありません。これには、Skype for Business Online とのフェデレーションを含むすべての展開が含まれます。
  
オンプレミスの展開では、ホストする各ドメインのフェデレーション DNS SRV レコードを公開する必要があります。 ガイダンスは、 [DNS の計画](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)で利用できます。 各ドメインは、ドメインのトップレベルのサフィックスが一致するエッジサーバーの FQDN への DNS SRV クエリによって解決される必要があります。 たとえば、ドメイン "contoso.com" を考えてみます。

|**有効な Fqdn**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |どちらの場合も、正確な FQDN は、エッジサーバーにインストールされている外部証明書の SN または SAN に存在する必要があります。   |
|access.contoso.com   ||
|**無効な Fqdn**|**Reason**|
|sip.contoso-edge.com   |サフィックスが一致しません。  |
|sip.it.contoso.com   |最上位のサフィックス一致ではありません。   |

外部証明書に関するその他のガイダンスについては、「[証明書の計画](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)」を参照してください。

#### <a name="faqs"></a>FAQ

**プロビジョニング web サイトがシャットダウンされるのはなぜですか?**
2006に展開されたパブリック IM (PIC) プロビジョニングメカニズム (pic.lync.com) は、では処理できなくなり、8/15/2019 でシャットダウンされます。 代わりに、パブリック IM フェデレーションでは、Skype for Business Online で使用されているものと同じフェデレーションモデル (「partner discovery」と呼ばれます) を想定しています。これは、オンプレミスの展開がフェデレーション DNS SRV レコードによって一般に検出されることを示します。

**この変更は、パブリック IM フェデレーションが廃止されたことを意味しますか。**
いいえ。 パブリック IM フェデレーションは、多くの場合、Skype for Business オンプレミス製品の寿命が終了するまで、今後もサポートされます。

**この会社では、Skype for Business Online とのハイブリッド関係 (共有アドレススペース) が影響を受けていますか?**
いいえ、既に Skype for Business Online とのフェデレーションを行っているため、この変更によって影響を受けることはありません。
 
**この変更は、会社が Skype for Business Online とのフェデレーションを有効にする必要があることを意味しますか。**
いいえ。 エッジサーバーのプロキシ設定で Skype for Business Online ホスティングプロバイダー (sipfed.online.lync.com) とのフェデレーションが有効になっていない場合、この変更による影響はありません。 ただし、skype for business Online とのフェデレーションに適用されるのと同じ DNS および証明書の要件は、Skype ユーザーとのフェデレーションにも適用されるようになりました。
 
**会社は大規模で、規制/コンプライアンス/その他の理由により、エッジ構成を変更できません。できること**
指定どおりにエッジサーバーの構成を変更できないオンプレミスの組織では、最も早い機会に製品サポートに到達する必要があります。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続の有効化 (PIC)

次に、skype for Business Server 環境と、Skype 接続を構成するために必要な管理タスクに重点を置いて説明します。 このセクションでは、管理者が Skype for Business Server を展開し、外部アクセス (エッジサーバーとも呼ばれる) を構成していることを前提としています。 
  
フェデレーションと PIC を有効にするには、3つの主要な手順が必要です。 それらを以下に示します。
  
1. フェデレーションと PIC を構成する
    
2. フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する
    
3. Skype PIC プロバイダー設定を構成する
    
#### <a name="1-configure-federation-and-pic"></a>1. フェデレーションと PIC を構成する

Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするには、フェデレーションが必要です。 パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Skype for Business ユーザーが Skype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、Skype for Business Server コントロールパネルを使用して構成されます。
  
> [!NOTE]
> PIC フェデレーションは、Lync Server 2010 (Live Communications Server、Office Communications Server) より前の製品リリースではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Skype for Business Server、Lync Server 2013、Lync Server 2010 があります。 
  
Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするには、フェデレーションが必要です。 パブリックインスタントメッセージング接続 (PIC) はフェデレーションのクラスであり、Skype for Business Server ユーザーが Skype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、図に示すように、Skype for Business Server コントロールパネルの [エッジ構成] ダイアログボックスを使用して構成します。
  
![新しいエッジプールの定義](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 検索を機能させるには、パブリックプロバイダー設定 (後の手順を参照) で、EnableSkypeIdRouting 属性と Enableskypeidrouting 属性を true に設定する必要があります。 
  
これで、サーバー上で実行する必要のある管理タスクが完了します。 これで、Skype 接続がセットアップされました。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. フェデレーションユーザーアクセスをサポートするように少なくとも1つのポリシーを構成する

Skype for Business Server コントロールパネルを使用して、管理者は1つ以上の外部ユーザーアクセスポリシーを構成し、Skype ユーザーが skype for Business Server の内部ユーザーと共同作業できるかどうかを制御する必要があります。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC プロバイダー設定を構成する

Skype for Business Server 管理シェルを使用して、管理者は skype for business クライアントポリシーを構成して、Skype for business を追加の PIC プロバイダーとして表示する必要があります。 
  
> [!NOTE]
> パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順の手順 2) を構成するまで、組織内の IM または会議に参加できません。 
  
新規インストールの場合は、図に示すように、skype for Business Server コントロールパネルを使用して skype パブリックプロバイダーを有効にすることで、Skype 接続を構成できます。
  
![SIP フェデレーション プロバイダー](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Skype for Business Server へのアップグレード時に Skype 接続を構成するには、既存の Skype パブリックプロバイダーを削除して再度追加する必要があります。 
  
Skype 接続の構成は、PowerShell のみを使用して行うこともできます。 PowerShell を使用して Skype 接続を構成するには:
  
1. Skype for business Server フロントエンドサーバーから、Skype for Business Server 管理シェルを開きます。
    
2. 次の2つのコマンドを実行します。
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 環境に PIC プロバイダがなく、新しい PIC プロバイダを作成している場合は、Enable-cspublicprovider コマンドレットを実行する必要はありません。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    明白なパラメーターは何か。
    
   - ProxyFqdn: Skype フェデレーションエッジの場所 (Microsoft によって所有/管理)
    
   - IconURL: &amp; skype 連絡先を視覚的に識別するために Lync Skype For business クライアントで使用されるアイコン
    
   - NameDecorationRoutingDomain and NameDecorationExcludedDomainList: setting を設定すると、ユーザーは、"msn.com" を使用して Microsoft 以外のドメインを装飾することを知らなくても、Skype ユーザーの MSAs 入力できます。 これにより、ExcludedDomainList に含まれていないすべてのドメインについて "user (contoso) @msn" と入力する必要がなくなります。 ドメインが除外リストに含まれていない場合、SfB クライアントは自動的に MSA をフォーマットします。 最も一般的な Microsoft アカウントドメインを除外リストに追加しました。
    
     > [!NOTE]
     > 変更が行われた場合は、パブリックプロバイダーを削除して、新しいものを追加する必要があります。 インプレース変更は許可されていません。 
  
     > [!NOTE]
     > Lync Server 2013 CU5 &amp; lync desktop client In Office 2013 SP1 では、NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、lync ユーザーが skype の連絡先を追加することによって、Microsoft 以外 @msn のドメインを識別して skype 形式にルーティングする必要がある状況を改善しました ()。 これらの新しい設定によって、NameDecorationRoutingDomain (現在は msn.com、live.com、Hotmail.com、outlook.com) のドメインが含まれていない場合は、[Skype 連絡先の追加] ダイアログボックスの [Skype 連絡先の追加] ダイアログボックスで、ユーザーの入力を自動書式設定することができます (msn.com に設定する必要があります)。 
  
3. Skype for Business クライアントのユーザーは、Skype ユーザーを検索して追加できるようになりました。
    
## <a name="clients-and-interoperability-matrix"></a>クライアントと相互運用性のマトリックス

次の表は、最新バージョンの Skype コンシューマーと Skype for Business の最新バージョンとの相互運用の状態を示しています。
  

|**Skype クライアント**|**連絡先、IM、プレゼンス、音声、ビデオ通話を追加する**|**Comment**|
|:-----|:-----|:-----|
|Skype Windows デスクトップ  <br/> |7.6 またはそれ以降、Windows XP 以降  <br/> |**NEW**: windows XP および windows Vista **(最新のクライアントバージョン7.26 以降を必要**とします) で実行されている windows Skype クライアント用のサポートが追加されました。 <br/> |
|Skype Mobile-Android 電話とタブレット  <br/> |6.19 以上 (Android OS バージョン4.0.3 以降を実行中)  <br/> |低仕様のデバイスでビデオ通話がサポートされない場合がある  <br/> |
|Skype Mobile-iOS  <br/> |6.11 またはそれ以上 (IOS 7 以降)  <br/> |サポートされていない iPhone 4 以前、iPod 第4世代以前、iPad 第1世代  <br/> |
|Skype Mac  <br/> |7.19 以降、Mac OS X 10.9 (Mavericks) 以降  <br/> |Mac OSX 10.9 またはそれ以上が必要です  <br/> |
|Skype Universal Windows アプリ (Windows 10) デスクトップおよびモバイル  <br/> |Windows 10 (Redstone 1 更新以降)  <br/> |Windows ユニバーサルアプリは、相互運用サポートを追加して、秋2016で更新プログラムを受け取ります  <br/> |
   
次の表に、skype for business の最新バージョンと Skype コンシューマーの最新バージョンとの相互運用の状態を示します。 
  
|**クライアント**|**Skype ディレクトリ検索と連絡先の追加**|**Skype A/V、IM 相互運用機能**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |はい  <br/> |はい  <br/> |
|Mac での Skype for Business  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync デスクトップ2013  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync Web App-オンラインとオンプレミス  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Mobile-Windows Phone  <br/> |近日公開  <br/> |はい  <br/> |
|Lync Mobile-Android  <br/> |近日公開  <br/> |はい  <br/> |
|Lync Mobile-iOS  <br/> |近日公開  <br/> |はい  <br/> |
|Lync Room System  <br/> |近日公開  <br/> |はい  <br/> |
|Lync モダンアプリ (Win 8.1)  <br/> |はい  <br/> |はい  <br/> |
|Lync Mac 2011  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync デスクトップ2010  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync Phone Edition  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Attendant  <br/> |該当なし  <br/> |該当なし  <br/> |
   
