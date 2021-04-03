---
title: Skype for Business Server での Skype 接続の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: Skype for Business Server と Skype コンシューマーを接続する方法について学習します。 Skype 接続とも呼ばれる。'
ms.openlocfilehash: 9c5f7f5c275b60c5b59dc43fe0a9b4a5c9b1514b
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574066"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Skype for Business Server での Skype 接続の展開

**概要:** Skype for Business Server と Skype コンシューマーを接続する方法について学習します。 Skype 接続とも呼ばれる。
  
この記事では、Skype Connectivity の展開について説明します。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>IT 担当者向け Skype Connectivity Overview

Skype Connectivity は、Skype for Business ユーザーが Skype ユーザーを検索して追加する機能を提供します。 Skype Connectivity は、Skype ユーザーとのフェデレーションおよびディレクトリ検索を有効にできる Skype for Business の機能です。 Skype Connectivity を有効にした後、Skype for Business ユーザーは Skype ユーザーを検索して追加できます。
  
## <a name="skype-directory-search"></a>Skype ディレクトリ検索

Skype Directory Search の機能により、Skype for Business ユーザーは Skype の連絡先を検索できます。 検索機能を使用すると、ユーザーは次の情報を使用して検索できます。
  
- **表示名で検索します。例: "John Doe"** - これは多くの結果を返す可能性があります。そのため、探している情報が見当たらされない可能性があります。
    
- **表示名と場所で検索します。たとえば"John Doe in バルセロナ"** - これにより、検索の結果が大幅に絞り込まれる可能性があります。
    
- **電子メールによる検索、"johndoe@outlook.com"** の例 - ほとんどの場合、結果は 1 つ返されます。指定した電子メールと完全に一致するメール。 ただし、同じメールが複数のアカウントに関連付けられている場合は、複数の結果が返される可能性があります。
    
- **電話番号で検索します。たとえば"123-123-1234"** - ほとんどの場合、結果は 1 つ返されます。指定した電話と完全に一致する電話機を指定します。 電話番号には国コード (1-xxx-yyy-zzzz) が含まれる必要があります。 同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返される場合があります。
    
- **Skype 名による検索、"JohnDoe1456"** の例 - 完全一致が見つかった場合は、最初の結果として返されます。 その他の可能性がある "名前" の一致が返される場合があります。
    
    > [!NOTE]
    > Skype Directory Search は、ポート 443 の 104.40.75.246、23.101.135.34、および 40.113.86.19 の IP アドレスと通信できる必要があります。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype Directory Search でサポートされる展開マトリックス

次の表に、Skype Directory Search のサポートの概要を示します。
  

||**Skype for Business Server フロントエンド**|**Lync Server 2013 (または古い) フロントエンド**|**コメント**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |サポートされている  <br/> |サポート対象外  <br/> |Skype for Business Server と Edge は、Skype ディレクトリ検索の前提条件です  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge のサイド バイ サイド展開  <br/> |サポートされている  <br/> |サポート対象外  <br/> |Skype Directory Search トラフィックは、Skype for Business Server Edge サーバーを通過します。 フェデレーション トラフィックは、管理者が構成したエッジを通過します。 たとえば、管理者は、Skype Directory Search をサポートしない Lync Server 2013 エッジ サーバーを通じてフェデレーション トラフィックの送信を続行できます。  <br/> |
|Lync Server 2013 (または古い) Edge  <br/> |サポート対象外  <br/> |サポート対象外  <br/> ||
   
> [!NOTE]
> Skype for Business Server フロントエンドで実行されているアドレス帳サービスは、エッジ サーバーに Skype Search ポート 4443 が存在することでエッジを検索します。 
  
> [!NOTE]
> 顧客がオンプレミス展開に複数のサイトを持ち、Skype for Business Server Edge サーバー/プールを 1 つのみ展開している場合は、すべてのサイトからの検索トラフィックが使用可能な 1 つのエッジ サーバーを通過します。 管理者は、すべてのサイトのプールが展開された Skype for Business Server Edge サーバー/プールにアクセスできる必要があります。 
  
> [!NOTE]
> Skype グラフ サービスは、要求レートが 15 要求/秒を超えた場合、オンプレミスまたは Microsoft 365 または Office 365 のお客様からの検索要求を調整します。 
  
> [!NOTE]
> 大規模なエンタープライズオンプレミスのお客様の場合、要求率を高くするには、Skype 検索サービスを使用してドメインを allowlist に追加する必要があります。
  
> [!NOTE]
> キューに保留中の要求が多すぎる場合、Skype for Business Server は受信要求を調整します。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Skype for Business Online の Skype Connectivity の展開

Skype Connectivity は、Microsoft 365 および Skype 365 の一部である Skype for Business Online のOfficeです。 Skype Connectivity 機能は、Microsoft 365 管理センター内の Skype for Business Administration Center から有効にできます。
  
Microsoft 365 Midsize Business の場合、Office 365 Enterprise、Microsoft 365 Education、および Office 365 for Government: Microsoft 365 管理センターにサインインし、Skype for Business Administration Center に移動します。 [外部通信] に移動します。 [パブリック IM サービス プロバイダー] で、[有効] をクリックします。 Skype Connectivity への個々のユーザー アクセスを制御する場合は、個々のユーザーの外部通信設定を編集して制御できます。
  
365 Office 365 Small Business Premium: Office 365 にサインインし、[管理サービス設定] インスタント メッセージング、会議、会議に \> \> 移動します。 [外部通信] をオンにする。 外部通信スイッチは、Skype Connectivity と、Skype for Business を使用する他の組織との通信の両方をオンにします。
  
Skype for Business Online 管理の詳細については、以下を参照してください。
  
- [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Im Skype for Business または Skype 外部連絡先ができない場合の試み](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Skype for Business で連絡先を追加する](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理者: 個々のユーザーの Skype for Business 設定を構成する](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Skype for Business Server の Skype Connectivity の展開

Skype for Business Server は、フェデレーション アクセス アーキテクチャを使用して Skype との接続をサポートします。 この接続により、Skype for Business Server ユーザーは Skype を追加できます。 Skype クライアントは、Skype for Business ユーザーを連絡先リストに追加できます。 Skype for Business Server で管理上設定されているポリシーに基づいて、ユーザーはインスタント メッセージングを使用して通信し、互いにプレゼンスを確認し、音声通話とビデオ通話を開始できます。 Skype 接続は Skype for Business Online の機能で、Microsoft 365 管理センター内の Skype for Business Administration Center から Skype for Business Online のお客様に対して有効にできます。
  
> [!NOTE]
> Skype for Business Server がパブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger に接続するように既に構成されている場合、展開は Skype 接続用に既に構成されています。 考慮する必要がある唯一の変更は、既存の Messenger PIC エントリの名前を Skype として変更する方法です。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Server パブリック IM 接続プロビジョニング サイトは使用できなくなりました

以前は、Skype for Business オンプレミス展開と Skype 間のフェデレーションを手動でプロビジョニングするために使用されたサイトは不要で、2019 年 8 月 15 日にシャットダウンされます。 Skype とのフェデレーションでは、フェデレーション パートナーの検出が利用されます。これは、Skype for Business Online とのフェデレーションに必要なのと同じメカニズムです。

既存のパブリック IM インフラストラクチャを介したオンプレミスの Skype for Business 展開と Skype ユーザー間の通信では、オンプレミスのエッジ サーバー構成が Skype for Business Online と互換性を持つ必要があります。

> [!NOTE]
> Skype for Business Online とフェデレーションを行うすべての展開を含め、ほとんどのお客様はアクションを実行する必要はありません。
  
ホストするドメインごとにフェデレーション DNS SRV レコードを発行するには、オンプレミス展開が必要です。 ガイダンスは DNS 計画 [で利用できます](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)。 各ドメインは、DNS SRV クエリによって、ドメインの上位レベルの接尾辞の一致を満たすエッジ サーバー FQDN に解決する必要があります。 たとえば、ドメイン "contoso.com" を考え出します。

|**有効な FQDN**|**コメント**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |いずれの場合も、エッジ サーバーにインストールされている外部証明書の SN または SAN に正確な FQDN が存在する必要があります。   |
|access.contoso.com   ||
|**無効な FQDN**|**理由**|
|sip.contoso-edge.com   |接尾辞の一致ではありません。  |
|sip.it.contoso.com   |トップ レベルの接尾辞の一致ではありません。   |

外部証明書に関する詳細なガイダンスについては、「証明書の計画」 [を参照してください](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)。

#### <a name="faqs"></a>FAQ

**プロビジョニング Web サイトがシャットダウンされる理由**
2006 年に展開されたパブリック IM (PIC) プロビジョニング メカニズム (pic.lync.com) はサービスを提供できなくなったので、2019 年 8 月 15 日にシャットダウンされます。 代わりに、パブリック IM フェデレーションは、Skype for Business Online で使用されるのと同じフェデレーション モデル ("パートナーの検出" と呼ばれる) を前提とします。この場合、オンプレミス展開はフェデレーション DNS SRV レコードによって一般に検出できます。

**この変更は、パブリック IM フェデレーションが廃止されるという意味ですか?**
いいえ。 パブリック IM フェデレーションは、おそらく Skype for Business オンプレミス製品が終了するまで、何年もサポートされ続けます。

**弊社は Skype for Business Online とのハイブリッド関係 (共有アドレス空間) を持っていますが、影響を受ける可能性がありますか?**
いいえ、Skype for Business Online と既にフェデレーションを行っている場合、この変更は影響を受け取らなくなっています。
 
**この変更は、Skype for Business Online とのフェデレーションを有効にする必要があるという意味ですか?**
いいえ。 エッジ サーバープロキシ設定で Skype for Business Online ホスティング プロバイダー (sipfed.online.lync.com) とのフェデレーションを有効にしない場合、この変更は影響しません。 ただし、Skype for Business Online とのフェデレーションに適用されるのと同じ DNS 要件と証明書要件は、Skype ユーザーとのフェデレーションにも適用されます。
 
**当社は大規模で、規制/コンプライアンス/その他の理由によりエッジ構成を変更できません。.何ができますか?**
指定したエッジ サーバー構成を変更できないオンプレミス組織は、できるだけ早く製品サポートに連絡する必要があります。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続の有効化 (PIC)

次に、Skype for Business Server 環境と、Skype Connectivity の構成に必要な管理タスクに注目します。 このセクションでは、管理者が Skype for Business Server を展開し、エッジ サーバーとも呼ばれる外部アクセスを構成したと仮定します。 
  
フェデレーションと PIC を有効にするには、3 つの主要な手順が必要です。 それらを次に示します。
  
1. フェデレーションと PIC の構成
    
2. フェデレーション ユーザー アクセスをサポートするポリシーを少なくとも 1 つ構成する
    
3. Skype PIC プロバイダーの設定を構成する
    
#### <a name="1-configure-federation-and-pic"></a>1. フェデレーションと PIC の構成

Skype ユーザーが組織内の Skype for Business ユーザーと通信するには、フェデレーションが必要です。 パブリック インスタント メッセージング接続 (PIC) はフェデレーションのクラスであり、Skype for Business ユーザーが Skype ユーザーと通信するように構成する必要があります。 フェデレーションと PIC は、Skype for Business Server コントロール パネルを使用して構成されます。
  
> [!NOTE]
> PIC フェデレーションは、Lync Server 2010 より前の製品リリース (Live Communication Server、Office通信サーバー) でサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Skype for Business Server、Lync Server 2013、Lync Server 2010 が含まれます。 
  
Skype ユーザーが組織内の Skype for Business ユーザーと通信するには、フェデレーションが必要です。 パブリック インスタント メッセージング接続 (PIC) はフェデレーションのクラスであり、Skype for Business Server ユーザーが Skype ユーザーと通信するように構成する必要があります。 フェデレーションと PIC は、図に示すように、Skype for Business Server コントロール パネルの [エッジ構成] ダイアログを使用して構成されます。
  
![新しいエッジ プールの定義](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 検索が機能するには、EnableSkypeIdRouting 属性と EnableSkypeDirectorySearch 属性をパブリック プロバイダー設定 (後の手順を参照) で true に設定する必要があります。 
  
これにより、サーバーで実行する必要がある管理タスクが完了します。 これで、Skype Connectivity 用にセットアップされています。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. フェデレーション ユーザー アクセスをサポートするポリシーを少なくとも 1 つ構成する

管理者は、Skype for Business Server コントロール パネルを使用して、1 つ以上の外部ユーザー アクセス ポリシーを構成して、Skype ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御する必要があります。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC プロバイダーの設定を構成する

管理者は、Skype for Business Server 管理シェルを使用して、Skype を追加の PIC プロバイダーとして表示する Skype for Business クライアント ポリシーを構成する必要があります。 
  
> [!NOTE]
> パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは、パブリック IM 接続をサポートするために少なくとも 1 つのポリシー (この手順の前の手順 2) も構成するまで、組織内の IM または会議に参加できません。 
  
新しいインストールでは、図に示すように Skype for Business Server コントロール パネルを使用して Skype パブリック プロバイダーを有効にすることで、Skype Connectivity を構成できます。
  
![SIP フェデレーション プロバイダー](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Skype for Business Server にアップグレードするときに Skype Connectivity を構成するには、既存の Skype パブリック プロバイダーを削除して再追加する必要があります。 
  
Skype Connectivity の構成は、PowerShell のみを使用して実行できます。 PowerShell を使用して Skype Connectivity を構成するには、次の手順を実行します。
  
1. Skype for Business Server フロントエンド サーバーから、Skype for Business Server 管理シェルを開きます。
    
2. 次の 2 つのコマンドを実行します。
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 環境に PIC プロバイダーが既に存在しない場合、新しい PIC プロバイダーを作成している場合は、このコマンドレットを実行Remove-CsPublicProvider必要があります。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    あまり明白ではないパラメーターは何をしますか?
    
   - ProxyFqdn: Skype フェデレーション エッジの場所 (Microsoft が所有/管理)
    
   - IconURL: Lync Skype for Business クライアントが Skype の連絡先を &amp; 視覚的に識別するために使用するアイコン
    
   - NameDecorationRoutingDomain と NameDecorationExcludedDomainList: これらを設定すると、ユーザーは"msn.com" で Microsoft 以外のドメインを "装飾" する必要なく、Skype ユーザーの MSA を入力できます。 これにより、ExcludedDomainList に含 user(contoso.com)@msn.com ドメインの "user(contoso.com)@msn.com" と入力する必要が無くなっています。 ドメインが除外リストに含めされていない場合、SfB クライアントは自動的に MSA の書式を設定します。 除外リストに最も一般的な Microsoft アカウント ドメインが追加されました。
    
     > [!NOTE]
     > 変更が行われた場合は、パブリック プロバイダーを削除して新しく追加する必要があります。 インプレイス変更は許可されません。 
  
     > [!NOTE]
     > Office 2013 SP1 の Lync Server 2013 CU5 Lync デスクトップ クライアントに追加された &amp; NameDecorationRoutingDomain と NameDecorationExcludedDomainList は、Lync ユーザーが Skype 以外のドメインを識別してルーティングするために必要な Skype 連絡先を追加して Skype (user(contoso.com)@msn.com の形式) にルーティングする状況を改善します。 NameDecorationExcludedDomainList (現在、msn.com、live.com、Hotmail.com、outlook.com) のドメインが含まれている場合、これらの新しい設定では、NameDecorationRoutingDomain (msn.com に設定する必要があります) と一緒に [Skype 連絡先の追加] ダイアログ ボックスでアドレス ユーザーの入力を自動的に書式設定できます。 
  
3. Skype for Business クライアント ユーザーは、Skype ユーザーを検索して追加できます。
    
## <a name="clients-and-interoperability-matrix"></a>クライアントと相互運用性マトリックス

次の表に、Skype コンシューマーの最新バージョンと Skype for Business の最新バージョンの相互運用の状態を示します。
  

|**Skype クライアント**|**連絡先、IM、プレゼンス、オーディオ、ビデオ通話を追加する**|**コメント**|
|:-----|:-----|:-----|
|Skype Windows デスクトップ  <br/> |7.6 以上、Windows XP 以上  <br/> |**NEW**: Windows XP で実行されている Windows Skype クライアントと Windows Vista のサポートが追加されました (最新のクライアント バージョン **7.26 以降が必要)** <br/> |
|Skype Mobile - Android Phone とタブレット  <br/> |6.19 以上、Android OS バージョン 4.0.3 以上を実行している  <br/> |低スペックデバイスがビデオ通話をサポートしていない可能性があります  <br/> |
|Skype Mobile - iOS  <br/> |IOS 7 以上で 6.11 以上  <br/> |サポートされていないのは、iPhone 4 以前、iPod 4th ジェネレーション以前、iPad 1st ジェネレーション  <br/> |
|Skype Mac  <br/> |Mac OS X 10.9 (Mavericks) 以上の 7.19 以上  <br/> |Mac OSX 10.9 以上が必要  <br/> |
|Skype ユニバーサル Windows アプリ (Windows 10) デスクトップとモバイル  <br/> |Windows 10 (Redstone 1 update 以降)  <br/> |Windows ユニバーサル アプリは、相互運用機能のサポートを追加する 2016 年秋に更新プログラムを受け取る  <br/> |
   
次の表に、Skype for Business の最新バージョンと Skype コンシューマーの最新バージョンの相互運用の状態を示します。 
  
|**クライアント**|**Skype ディレクトリ検索と連絡先の追加**|**Skype A/V、IM 相互運用**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |はい  <br/> |はい  <br/> |
|Mac 版 Skype for Business  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync Desktop 2013  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync Web App - オンラインおよびオンプレミス  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Mobile - Windows Phone  <br/> |近日公開  <br/> |はい  <br/> |
|Lync Mobile - Android  <br/> |近日公開  <br/> |はい  <br/> |
|Lync Mobile - iOS  <br/> |近日公開  <br/> |はい  <br/> |
|Lync Room System  <br/> |近日公開  <br/> |はい  <br/> |
|Lync モダン アプリ (Win 8.1)  <br/> |はい  <br/> |はい  <br/> |
|Lync Mac 2011  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync Desktop 2010  <br/> |追加可能 (検索なし)  <br/> |はい  <br/> |
|Lync Phone Edition  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Attendant  <br/> |該当なし  <br/> |N/A  <br/> |
   
