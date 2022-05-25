---
title: Skype for Business ServerにSkype接続をデプロイする
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: Skype for Business ServerをSkypeコンシューマーに接続する方法について説明します。 Skype接続とも呼ばれます。'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671683"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Skype for Business ServerにSkype接続をデプロイする

**概要：** SkypeコンシューマーとSkype for Business Serverを接続する方法について説明します。 Skype接続とも呼ばれます。
  
この記事では、Skype接続のデプロイについて説明します。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>SKYPE IT プロフェッショナル向けの接続の概要

Skype接続では、Skype for Businessユーザーに対して、Skype ユーザーを検索および追加する機能を提供します。 Skype接続は、Skype ユーザーとのフェデレーションとディレクトリ検索を有効にできるSkype for Businessの機能です。 Skype接続を有効にすると、Skype for Business ユーザーはSkypeユーザーを検索して追加できるようになります。
  
## <a name="skype-directory-search"></a>Skype ディレクトリ検索

Skype ディレクトリ検索機能を使用すると、Skype for BusinessユーザーはSkype連絡先を検索できます。 検索機能を使用すると、ユーザーは次を使用して検索できます。
  
- **表示名 ("John Doe" など) で検索** する - 多くの結果が返される可能性があるため、探しているものが見つからない可能性があります。
    
- **表示名と場所で検索します(例: "John Doe in Barcelona"** - これにより、検索結果が大幅に絞り込まれます。
    
- **"johndoe@outlook.com" などの電子メールで検索** する - ほとんどの場合、1 つの結果が返されます。指定した電子メールと正確に一致するもの。 ただし、同じメールが複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。
    
- **電話番号 (例: "123-123-1234" で検索する)** - ほとんどの場合、1 つの結果が返されます。指定した電話に正確に一致するもの。 電話番号には国番号 (1-xxx-yyy-zzzz) を含める必要があります。 同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。
    
- **[名前Skype検索] (例: "JohnDoe1456"** ) - 完全一致が見つかった場合は、最初の結果として返されます。 他の可能な "名前" 一致が返される可能性があります。
    
    > [!NOTE]
    > Skype ディレクトリ検索は、ポート 443(104.40.75.246、23.101.135.34、40.113.86.19) で次の IP アドレスと通信できる必要があります。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype ディレクトリ検索でサポートされているデプロイ マトリックス

次の表に、Skype ディレクトリ検索のサポートの概要を示します。
  

|&nbsp;|Skype for Business Server フロント エンド|Lync Server 2013 (またはそれ以前の) フロントエンド|コメント|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |サポート   |サポート対象外   |Skype for Business Serverと Edge は、Skype ディレクトリ検索の前提条件です   |
|Skype for Business Server Edge + Lync Server 2013 Edge を並べて展開   |サポート   |サポート対象外   |Skype Directory Search トラフィックは、Skype for Business Server Edge サーバーを経由します。 フェデレーション トラフィックは、管理者によって構成されたエッジを経由します。 たとえば、管理者は、ディレクトリ検索Skypeサポートしない Lync Server 2013 Edge サーバーを介してフェデレーション トラフィックを送信し続けることができます。   |
|Lync Server 2013 (またはそれ以前の) Edge   |サポート対象外   |サポート対象外   ||
   
> [!NOTE]
> Skype for Business Server フロント エンドで実行されているアドレス帳サービスは、エッジ サーバーにSkype検索ポート 4443 が存在することでエッジを検索します。 
  
> [!NOTE]
> オンプレミスの展開に複数のサイトがあり、1 つのSkype for Business Server Edge サーバー/プールのみを展開した場合、すべてのサイトからの検索トラフィックは、使用可能な 1 つのエッジ サーバーを経由します。 管理者は、すべてのサイトのプールが、展開された Skype for Business Server Edge サーバー/プールにアクセスできることを確認する必要があります。 
  
> [!NOTE]
> Skype graph サービスは、要求率が 15 要求/秒を超えた場合、オンプレミスまたはMicrosoft 365またはOffice 365顧客からの検索要求を調整します。 
  
> [!NOTE]
> 大企業のオンプレミスのお客様の場合は、要求率を高めるために、Skype検索サービスを使用してドメインを許可リストに追加する必要があります。
  
> [!NOTE]
> キューに保留中の要求が多すぎる場合、Skype for Business Serverは受信要求を調整します。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Skype for Business Online のSkype接続のデプロイ

Skype接続は、Microsoft 365とOffice 365の一部であるSkype for Business Online の機能でもあります。 Microsoft 365 管理センター内のSkype for Business管理センターから、Skype接続機能を有効にすることができます。
  
政府機関向けのMicrosoft 365中規模ビジネス、Office 365 Enterprise、Microsoft 365 Education、Office 365の場合: Microsoft 365 管理センターにサインインし、Skype for Business管理センター。 外部通信に移動します。 [パブリック IM サービス プロバイダー] の [有効] をクリックします。 Skype接続への個々のユーザー アクセスを制御するには、個々のユーザーの外部通信設定を編集します。
  
Office 365 Small Business Premium: Office 365にサインインし、管理 Service 設定 \> \> インスタント メッセージング、会議、会議に移動します。 外部通信を有効にします。 外部通信スイッチは、Skype接続と、Skype for Businessを使用する他の組織との通信の両方をオンにします。
  
Skype for Businessオンライン管理の詳細については、次を参照してください。
  
- [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [外部連絡先を IM Skype for BusinessまたはSkypeできない場合の試し](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Skype for Businessに連絡先を追加する](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理者: 個々のユーザーのSkype for Business設定を構成する](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Skype for Business ServerのSkype接続のデプロイ

Skype for Business Serverでは、フェデレーション アクセス アーキテクチャを使用して、Skypeとの接続をサポートします。 この接続により、Skype for Business Server ユーザーはSkypeを追加できます。 Skype クライアントは、Skype for Businessユーザーを連絡先リストに追加することもできます。 管理者がSkype for Business Serverに設定されたポリシーに基づいて、ユーザーはインスタント メッセージングを使用して通信し、相互のプレゼンスを確認し、音声通話とビデオ通話を開始できます。 Skype接続は、Skype for Business Online の機能でもあり、Microsoft 365 管理センター内のSkype for Business管理センターからSkype for Business Online のお客様に対して有効にできます。
  
> [!NOTE]
> パブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger に接続するようにSkype for Business Serverが既に構成されている場合、デプロイは既にSkype接続用に構成されています。 考慮する必要がある唯一の変更は、既存の Messenger PIC エントリの名前をSkypeに変更することだけです。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Serverパブリック IM 接続プロビジョニング サイトは使用できなくなりました

以前は、Skype for BusinessオンプレミスのデプロイとSkypeの間のフェデレーションを手動でプロビジョニングするために使用されていたサイトは不要になり、2019 年 8 月 15 日にシャットダウンされます。 Skypeとのフェデレーションでは、フェデレーション パートナーの検出が利用されるようになりました。これは、Skype for Business Online とのフェデレーションに必要なメカニズムと同じです。

オンプレミスのSkype for Business展開と既存のパブリック IM インフラストラクチャを介したSkypeユーザー間の通信では、オンプレミスの Edge Server 構成をSkype for Business Online と互換性を持つ必要があります。

> [!NOTE]
> ほとんどのお客様は、Skype for Business Online とフェデレーションするすべてのデプロイを含め、アクションは必要ありません。
  
オンプレミスのデプロイは、ホストする各ドメインのフェデレーション DNS SRV レコードを発行するために必要です。 ガイダンスは、 [DNS 計画](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)で入手できます。 各ドメインは、DNS SRV クエリによって、ドメインの最上位のサフィックス一致を満たすエッジ サーバー FQDN に解決する必要があります。 たとえば、ドメイン "contoso.com" を考えてみましょう。

|**有効な FQDN**|**コメント**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |いずれの場合も、エッジ サーバーにインストールされている外部証明書の SN または SAN に正確な FQDN が存在する必要があります。   |
|access.contoso.com   ||
|**無効な FQDN**|**理由**|
|sip.contoso-edge.com   |サフィックスが一致しません。  |
|sip.it.contoso.com   |最上位のサフィックスの一致ではありません。   |

外部証明書に関する詳細なガイダンスについては、「 [証明書の計画」を参照してください](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)。

#### <a name="faqs"></a>FAQ

**プロビジョニング Web サイトがシャットダウンされている理由**
2006 年にデプロイされたパブリック IM (PIC) プロビジョニング メカニズム (pic.lync.com) はサービス可能でなくなり、2019 年 8 月 15 日にシャットダウンされます。 代わりに、パブリック IM フェデレーションは、Skype for Business Online によって使用されるのと同じフェデレーション モデル ("パートナー検出" と呼ばれます) を前提としています。これにより、オンプレミスのデプロイはフェデレーション DNS SRV レコードによってパブリックに検出できます。

**この変更は、パブリック IM フェデレーションが非推奨になっていることを意味しますか?**
いいえ。 パブリック IM フェデレーションは、おそらくオンプレミス製品のSkype for Businessが終了するまで、長年にわたって引き続きサポートされます。

**Microsoft の会社は、Skype for Business Online とのハイブリッドリレーションシップ (共有アドレス空間) を持っています。影響を受けるのですか?**
いいえ。既にSkype for Business Online とフェデレーションしているため、この変更は影響を受けなくなります。
 
**この変更は、会社が Skype for Business Online とのフェデレーションを有効にする必要があることを意味しますか?**
いいえ。 エッジ サーバー プロキシ設定で Skype for Business Online ホスティング プロバイダー (sipfed.online.lync.com) とのフェデレーションが有効になっていない場合、この変更は影響しません。 ただし、Skype for Business Online とのフェデレーションに適用されるのと同じ DNS と証明書の要件は、Skype ユーザーとのフェデレーションにも適用されるようになりました。
 
**当社は大規模であり、規制/コンプライアンス/その他の理由によりエッジ構成を変更できません...何ができますか?**
指定したエッジ サーバー構成を変更できないオンプレミスの組織は、できるだけ早い機会に製品サポートに連絡する必要があります。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続の有効化 (PIC)

次に、Skype接続を構成するために必要なSkype for Business Server環境と管理タスクに焦点を当てます。 このセクションでは、管理者がSkype for Business Serverを展開し、外部アクセス (エッジ サーバーとも呼ばれます) を構成していることを前提としています。 
  
フェデレーションと PIC を有効にするには、3 つの主要な手順が必要です。 それらを次に示します。
  
1. フェデレーションと PIC を構成する
    
2. フェデレーション ユーザー アクセスをサポートするように少なくとも 1 つのポリシーを構成する
    
3. Skype PIC プロバイダー設定を構成する
    
#### <a name="1-configure-federation-and-pic"></a>1. フェデレーションと PIC を構成する

フェデレーションは、Skype ユーザーが組織内のSkype for Businessユーザーと通信できるようにするために必要です。 パブリック インスタント メッセージング接続 (PIC) はフェデレーションのクラスであり、Skype for Business ユーザーがSkype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、Skype for Business Server コントロール パネルを使用して構成されます。
  
> [!NOTE]
> PIC フェデレーションは、Lync Server 2010 (Live Communication Server、Office Communications Server) より前の製品リリースではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Skype for Business Server、Lync Server 2013、Lync Server 2010 などがあります。 
  
フェデレーションは、Skype ユーザーが組織内のSkype for Businessユーザーと通信できるようにするために必要です。 パブリック インスタント メッセージング接続 (PIC) はフェデレーションのクラスであり、Skype for Business Server ユーザーがSkype ユーザーと通信できるように構成する必要があります。 フェデレーションと PIC は、図に示すように、Skype for Business Server コントロール パネルの [エッジ構成] ダイアログを使用して構成されます。
  
![新しいエッジ プールを定義します。](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> EnableSkypeIdRouting 属性と EnableSkypeDirectorySearch 属性は、検索を機能させるには、パブリック プロバイダーの設定 (後の手順を参照) で true に設定する必要があります。 
  
これで、サーバーで実行する必要がある管理タスクが完了します。 これで、Skype Connectivity の設定が完了しました。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. フェデレーション ユーザー アクセスをサポートするように少なくとも 1 つのポリシーを構成する

Skype for Business Server コントロール パネルを使用して、管理者は 1 つ以上の外部ユーザー アクセス ポリシーを構成して、Skype ユーザーが内部Skype for Business Server ユーザーと共同作業できるかどうかを制御する必要があります。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC プロバイダー設定を構成する

Skype for Business Server管理シェルを使用して、管理者は、追加の PIC プロバイダーとしてSkypeを表示するようにSkype for Business クライアント ポリシーを構成する必要があります。 
  
> [!NOTE]
> パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは、パブリック IM 接続をサポートするために少なくとも 1 つのポリシー (この手順の前の手順 2) も構成するまで、組織内の IM または会議に参加できません。 
  
新しいインストールの場合は、図に示すようにSkype for Business Server コントロール パネルを使用してSkypeパブリック プロバイダーを有効にすることで、Skype接続を構成できます。
  
![SIP フェデレーション プロバイダー。](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Skype for Business ServerにアップグレードするときにSkype接続を構成するには、既存のSkypeパブリック プロバイダーを削除して再追加する必要があります。 
  
Skype接続の構成は、PowerShell のみを使用して行うこともできます。 PowerShell を使用してSkype接続を構成するには:
  
1. Skype for Business Server フロント エンド サーバーから、Skype for Business Server管理シェルを開きます。
    
2. 次の 2 つのコマンドを実行します。
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 環境にまだ PIC プロバイダーが存在せず、新しい PIC プロバイダーを作成している場合は、Remove-CsPublicProvider コマンドレットを実行する必要はありません。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    あまりわかりやすいパラメーターは何をしますか?
    
   - ProxyFqdn: Skype フェデレーション エッジの場所 (Microsoft が所有/管理)
    
   - IconURL: Lync &amp; Skype for Business クライアントがSkype連絡先を視覚的に識別するために使用するアイコン
    
   - NameDecorationRoutingDomain と NameDecorationExcludedDomainList: これらを設定すると、ユーザーは"msn.com" で Microsoft 以外のドメインを "装飾" する必要なく、Skype ユーザーの MSA を入力できます。 これにより、ExcludedDomainList に含まれていないすべてのドメインに「user(contoso.com)@msn.com」と入力する必要がなくなります。 ドメインが [除外] リストにない場合、SfB クライアントは自動的に MSA の書式を設定します。 除外リストに最も一般的な Microsoft アカウント ドメインを追加しました。
    
     > [!NOTE]
     > 変更が加えられた場合は、パブリック プロバイダーを削除し、新しく追加する必要があります。 インプレース変更は許可されません。 
  
     > [!NOTE]
     > Office 2013 SP1 の Lync Server 2013 CU5 &amp; Lync デスクトップ クライアントに追加された NameDecorationRoutingDomain と NameDecorationExcludedDomainList により、Lync ユーザーが Microsoft 以外のドメインを識別してSkypeに "装飾" するために必要な Skype連絡先を追加する状況が改善されます (user(contoso.com)@msn.com の形式)。 これらの新しい設定では、NameDecorationExcludedDomainList のドメインが含まれていない場合は、NameDecorationRoutingDomain (msn.com に設定する必要があります) を使用して [連絡先の Skype追加] ダイアログ ボックスにアドレス ユーザーの入力を自動的に書式設定できます (現在、msn.com、live.com、Hotmail.com、outlook.com をサポートできます)。 
  
3. Skype for Business クライアント ユーザーから、Skype ユーザーを検索して追加できるようになりました。
    
## <a name="clients-and-interoperability-matrix"></a>クライアントと相互運用性マトリックス

次の表は、Skype コンシューマーの最新バージョンと最新バージョンのSkype for Businessの間の相互運用の状態を示しています。
  

|Skype クライアント|連絡先、IM、プレゼンス、オーディオ、ビデオ通話を追加する|コメント|
|:-----|:-----|:-----|
|デスクトップのSkype Windows   |7.6 以上、Windows XP 以上   |**NEW**: Windows XP および Windows Vista で実行されているWindows Skype クライアントのサポート **が追加されました (最新のクライアント バージョン 7.26 以降が必要)**  |
|Skype Mobile - Android 電話とタブレット   |OS バージョン 4.0.3 以降Android実行されている 6.19 以降   |低スペックデバイスでは、ビデオ通話がサポートされない場合があります   |
|Skype Mobile - iOS   |6.11 以降(IOS 7 以降)   |サポートされていないiPhone 4 以前、iPod 4 番目の世代以前、iPad第 1 世代   |
|mac Skype   |7.19 以上、Mac OS X 10.9 (Mavericks) 以上   |Mac OSX 10.9 以降が必要   |
|Skype ユニバーサル Windows アプリ (Windows 10) デスクトップとモバイル   |Windows 10 (Redstone 1 以降の更新プログラム)   |Windowsユニバーサル アプリは、相互運用機能のサポートを追加する 2016 年秋に更新プログラムを受け取ります   |
   
次の表は、最新バージョンのSkype for Businessと最新バージョンのSkypeコンシューマーの間の相互運用の状態を示しています。 
  
|クライアント|Skype ディレクトリの検索と連絡先の追加|Skype A/V、IM 相互運用機能|
|:-----|:-----|:-----|
|Skype for Business   |はい   |はい   |
|Mac 版 Skype for Business   |追加可能 (検索なし)   |はい   |
|Lync Desktop 2013   |追加可能 (検索なし)   |はい   |
|Lync Web App - オンラインとオンプレミス   |該当なし   |該当なし   |
|Lync Mobile - Windows Phone   |近日公開   |はい   |
|Lync Mobile - Android   |近日公開   |はい   |
|Lync Mobile - iOS   |近日公開   |はい   |
|Lync Room System   |近日公開   |はい   |
|Lync Modern App (Win 8.1)   |はい   |はい   |
|Lync Mac 2011   |追加可能 (検索なし)   |はい   |
|Lync Desktop 2010   |追加可能 (検索なし)   |はい   |
|Lync Phone Edition   |該当なし   |該当なし   |
|Lync Attendant   |該当なし   |N/A   |
   
