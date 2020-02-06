---
title: Skype for Business Server に Skype の接続を展開する
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
description: '概要: skype for Business Server を Skype コンシューマーと接続する方法について説明します。 これは、Skype 接続とも呼ばれます。'
ms.openlocfilehash: e9c8a83b24ddbed95f2fd16f2f11b887f2241625
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798104"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Skype for Business Server に Skype の接続を展開する

**概要:** Skype for business Server を Skype コンシューマーに接続する方法について説明します。 これは、Skype 接続とも呼ばれます。
  
ここでは、Skype Connectivity の展開について順を追って説明します。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Connectivity の概要 (IT 担当者向け)

Skype 接続を使うと、skype for Business ユーザーが Skype ユーザーを検索して追加することができます。 Skype 接続は skype for Business の機能で、Skype ユーザとのフェデレーションおよびディレクトリ検索を有効にすることができます。 Skype の接続を有効にすると、skype for Business ユーザーは skype ユーザを検索して追加できるようになります。
  
## <a name="skype-directory-search"></a>Skype Directory Search

Skype Directory Search 機能によって、Skype for Business ユーザーは、Skype の連絡先を検索できます。検索機能により、ユーザーは以下の手段を使用して検索を実行できます。
  
- **表示名、"John Doe" の例で検索**すると、多くの結果が返される可能性があるため、探している情報が見つからないことがあります。
    
- **表示名と場所を指定して検索します。たとえば、"John Doe In スペインバルセロナ"** のように指定します。これにより、検索結果を大幅に絞り込むことができます。
    
- **メールで検索して、"johndoe@outlook.com"** のようにします。ほとんどの場合、これは1つの結果を返します。指定したメールと完全に一致するもの。 ただし、同じメールが複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。
    
- **電話番号で検索します。 "123-123-1234"** のようにします。ほとんどの場合、これは1つの結果を返します。指定した電話と正確に一致するもの。 電話番号には国コードを含める必要があります (例: xxx-yyy-zzzz)。 同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返されることがあります。
    
- **Skype 名で検索します。 "JohnDoe1456"** のように指定します。完全一致が見つかった場合は、最初の結果として返されます。 その他の可能性のある "名前" の一致は、返される可能性があります。
    
    > [!NOTE]
    > Skype Directory Search では、ポート 443 で IP アドレス 104.40.75.246、23.101.135.34、40.113.86.19 と通信できる必要があります。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype Directory Search のサポートされる展開のマトリックス

以下の表に、Skype Directory Search のサポートの概要を示します。
  

||**Skype for Business Server のフロントエンド**|**Lync Server 2013 (またはそれ以降の) フロントエンド**|**コメント**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |サポート対象  <br/> |サポート対象外  <br/> |Skype for Business Server と Edge は Skype ディレクトリ検索の前提条件です  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge が並列で展開されている  <br/> |サポート対象  <br/> |サポート対象外  <br/> |Skype Directory Search のトラフィックは Skype for Business Server エッジ サーバーを通過します。フェデレーション トラフィックは、管理者により構成されたエッジを通過します。たとえば、管理者は、Skype Directory Search をサポートしない Lync Server 2013 エッジ サーバーを介してフェデレーション トラフィックを引き続き送信することを選択できます。  <br/> |
|Lync Server 2013 (またはそれ以降の) エッジ  <br/> |サポート対象外  <br/> |サポート対象外  <br/> ||
   
> [!NOTE]
> Skype for Business Server のフロントエンドで実行されている電話帳サービスは、エッジサーバーの Skype 検索ポート4443の存在によってエッジを検索します。 
  
> [!NOTE]
> 顧客がオンプレミスの展開に複数のサイトを持っていて、1つの Skype for Business Server Edge サーバー/プールのみを展開している場合、すべてのサイトからのトラフィックの検索は、利用可能な1つのエッジサーバーを経由します。 管理者は、展開された Skype for Business Server Edge サーバー/プールに、すべてのサイトのプールがアクセスできることを確認する必要があります。 
  
> [!NOTE]
> Skype グラフ サービスは、要求レートが 15 要求/秒を超えた場合、すべてのオンプレミスまたは Office 365 カスタマーからの検索要求を調整します。 
  
> [!NOTE]
> 大規模エンタープライズ オンプレミス カスタマーに対しては、より高い要求レートを許可するために、ドメインを Skype 検索サービスのホワイトリストに登録する必要があります。 
  
> [!NOTE]
> キューに保留中の要求が多すぎると、Skype for Business Server によって着信要求が抑制されます。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Office 365 での Skype for Business Server Online 用の Skype Connectivity の展開

Skype Connectivity は、Office 365 の一部である Skype for Business Online の機能でもあります。Office 365 ポータル内の Skype for Business 管理センターから、Skype Connectivity 機能を有効にすることができます。
  
Office 365 中堅企業向け、Office 365 Enterprise、Office 365 エデュケーション、office 365 for Government: Office 365 ポータルにサインインして、Skype for Business 管理センターに移動します。 外部通信に移動します。 [パブリック IM サービスプロバイダー] で [有効にする] をクリックします。 個人ユーザの Skype 接続へのアクセスを制御するには、個々のユーザの外部通信設定を編集します。
  
Office 365 Small Business Premium の場合: Office 365 にサインインし、[管理者\>サービスの\>設定] で [インスタントメッセージング、会議、会議] に移動します。 外部通信を有効にします。 [外部通信] スイッチは、skype for Business を使用する他の組織との Skype 接続と通信の両方を有効にします。
  
Skype for Business Online の管理の詳細については、次の記事を参照してください。
  
- [ユーザーが外部の Skype for Business ユーザーに連絡できるようにする](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Skype for Business または Skype の外部連絡先に IM できない場合の対応策](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Skype for Business で連絡先を追加する](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理者: 個別のユーザーの Skype for Business の設定を構成する](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Skype for Business Server 向けの Skype 接続の展開

Skype for Business Server は、フェデレーションアクセスアーキテクチャを使用して、Skype との接続をサポートします。 この接続によって、Skype for Business Server ユーザーは Skype を追加できます。 Skype クライアントは、Skype for Business ユーザをコンタクトリストに追加することもできます。 Skype for Business Server ユーザーは、管理者が設定したポリシーに基づいて、インスタントメッセージを使ってコミュニケーションを行い、互いのプレゼンスを確認して、音声通話とビデオ通話を開始することができます。 Skype 接続は、skype for Business Online の機能でもあり、Office 365 ポータル内の Skype for Business 管理センターから Skype for business Online のお客様に対して有効にすることができます。
  
> [!NOTE]
> Skype for Business Server がパブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は、既に Skype Connectivity 用に構成されています。検討が必要と思われるのは、既存の Messenger PIC エントリの名前を Skype などに変更することだけです。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Server パブリック IM 接続プロビジョニングサイトは利用できなくなりました

以前は Skype for Business のオンプレミス展開の間でフェデレーションを手動でプロビジョニングするために使用されていたサイト。 Skype は不要になったため、8/15/2019 でシャットダウンされます。 Skype とのフェデレーションでは、フェデレーションパートナー検出が利用されるようになりました。これは、Skype for Business Online とのフェデレーションに必要なメカニズムと同じです。

既存のパブリック IM インフラストラクチャを使用して、オンプレミスの Skype for Business 展開と Skype ユーザー間の通信を行うには、オンプレミスエッジサーバー構成が Skype for Business Online と互換性がある必要があります。

> [!NOTE]
> ほとんどのお客様は、Skype for Business Online とフェデレーションされているすべての展開を含む、何もする必要はありません。
  
オンプレミスの展開は、ホストしている各ドメインのフェデレーション DNS SRV レコードを公開するために必要です。 ガイダンスは DNS の[計画](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)で利用できます。 各ドメインは、DNS SRV クエリによって、ドメインの最上位レベルのサフィックス一致を満たすエッジサーバーの FQDN に解決する必要があります。 たとえば、"contoso.com" というドメインを考えます。

|**有効な Fqdn**|**コメント**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |どちらの場合も、正確な FQDN が、エッジサーバーにインストールされている外部証明書の SN または SAN に存在している必要があります。   |
|access.contoso.com   ||
|**無効な Fqdn**|**理由**|
|sip.contoso-edge.com   |サフィックスの一致ではありません。  |
|sip.it.contoso.com   |トップレベルのサフィックスの一致ではありません。   |

外部証明書に関するその他のガイダンスについては、「[証明書の計画](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)」をご覧ください。

#### <a name="faqs"></a>社外

**プロビジョニング web サイトがシャットダウンされるのはなぜですか?**
2006に展開されたパブリック IM (PIC) プロビジョニングメカニズム (pic.lync.com) は処理されなくなり、8/15/2019 でシャットダウンされます。 代わりに、パブリック IM フェデレーションは、"パートナー検出" と呼ばれる Skype for Business Online で使用されているものと同じフェデレーションモデルを想定し、オンプレミスの展開はフェデレーション DNS SRV レコードによって公開されます。

**この変更は、パブリック IM フェデレーションが廃止されていることを意味しますか?**
いいえ。 パブリック IM フェデレーションは、多くの場合、Skype for Business オンプレミス製品が終了するまで、引き続きサポートされます。

**会社では、Skype for Business Online との間にハイブリッド関係 (共有アドレススペース) を使用していますが、影響はありますか?**
いいえ。既に Skype for Business Online とのフェデレーションを行っているため、この変更によって影響を受けることはありません。
 
**この変更は、会社が Skype for Business Online とのフェデレーションを有効にする必要があることを意味しますか?**
いいえ。 Edge サーバーのプロキシ設定で、Skype for Business Online ホスティングプロバイダー (sipfed.online.lync.com) とのフェデレーションを有効にしない場合、この変更による影響はありません。 ただし、Skype for Business Online とのフェデレーションに適用されるのと同じ DNS と証明書の要件は、Skype ユーザーとのフェデレーションにも適用されるようになりました。
 
**会社は大規模で、規制/コンプライアンス/その他の理由により、エッジ構成を変更することはできません。何ができますか?**
指定されたとおりにエッジサーバーの構成を変更できないオンプレミスの組織は、最も早い機会で製品サポートに連絡する必要があります。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続 (PIC) の有効化

次は、Skype for Business Server 環境と、Skype の接続を構成するために必要な管理タスクに重点を置いています。 このセクションでは、管理者は Skype for Business Server を展開し、外部アクセス (エッジ サーバーとも呼ばれます) を構成していることを前提としています。 
  
フェデレーションと PIC を有効にするために必要な主な 3 つのステップは次のとおりです。
  
1. フェデレーションと PIC を構成する
    
2. フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する
    
3. Skype PIC プロバイダー設定を構成する
    
#### <a name="1-configure-federation-and-pic"></a>1. フェデレーションと PIC を構成する

フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、Skype for Business Server コントロール パネルを使用して構成します。
  
> [!NOTE]
> PIC フェデレーションは、Lync Server 2010 (Live Communications Server、Office Communications Server) より前の製品リリースでサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Skype for Business Server、Lync Server 2013、Lync Server 2010 が含まれています。 
  
フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、次に示すように Skype for Business Server コントロール パネルの [エッジ構成] ダイアログを使用して構成します。
  
![新しいエッジ プールの定義](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 検索を使用するには、パブリック プロバイダーの設定 (後の手順を参照) で EnableSkypeIdRouting 属性と EnableSkypeDirectorySearch 属性を True に設定する必要があります。 
  
これで、サーバー上で実行する必要がある管理タスクが完了し、Skype Connectivity を使用するように設定されました。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. フェデレーションされたユーザーアクセスをサポートするように、少なくとも1つのポリシーを構成する

管理者は Skype for Business Server コントロール パネルを使用して外部ユーザー アクセス ポリシーを 1 つ以上構成し、Skype ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御する必要があります。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC プロバイダ設定を構成する

管理者は Skype for Business Server 管理シェルを使用して Skype for Business クライアント ポリシーを構成し、Skype を追加の PIC プロバイダーとして表示する必要があります。 
  
> [!NOTE]
> パブリックインスタントメッセージング接続 (PIC) サービスプロバイダーのユーザーは、パブリック IM 接続をサポートするために、少なくとも1つのポリシー (この手順では、前の手順 2) を構成するまで、組織内の IM または会議に参加することはできません。 
  
新規インストールの場合は、図に示すように Skype for Business Server コントロール パネルを使用して Skype パブリック プロバイダーを有効にすることで、Skype Connectivity を構成することができます。
  
![SIP フェデレーション プロバイダー](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Skype for Business Server にアップグレードする場合に Skype Connectivity を構成するには、既存の Skype パブリック プロバイダーを削除してから再度追加する必要があります。 
  
Skype Connectivity の構成は、PowerShell のみを使用して行うこともできます。PowerShell を使用して Skype Connectivity を構成するには、次の手順に従います。
  
1. Skype for Business Server フロントエンド サーバーから、Skype for Business Server 管理シェルを開きます。
    
2. 次の 2 つのコマンドを実行します。
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 環境にまだ PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、Remove-CsPublicProvider コマンドレットを実行する必要はありません。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    意味がわかりにくいパラメーターの動作
    
   - ProxyFqdn:  (Microsoft により所有/維持管理される) Skype フェデレーション エッジの場所
    
   - IconURL: Lync &amp; Skype for business クライアントが skype の連絡先を視覚的に識別するために使用するアイコン
    
   - NameDecorationRoutingDomain と NameDecorationExcludedDomainList: setting を設定すると、ユーザーは "msn.com" で、Microsoft 以外のドメインを "装飾" していることを知らなくても、Skype ユーザーの MSAs を入力することができます。 これにより、ExcludedDomainList にないすべてのドメインに対して「user (contoso) @msn」と入力する必要がなくなります。 ドメインが除外リストに存在しない場合、SfB クライアントは自動的に MSA を書式設定します。 最も一般的な Microsoft アカウントドメインを除外リストに追加しました。
    
     > [!NOTE]
     > 変更が行われた場合は、パブリック プロバイダーを削除して新しく追加する必要があります。 インプレースでの変更は許可されていません。 
  
     > [!NOTE]
     > Lync Server 2013 CU5 以降&amp; lync デスクトップクライアントに OFFICE 2013 SP1 で追加されました。 lync ユーザーが skype の連絡先を追加するには、Microsoft 以外のドメインを "装飾" して、skype (ユーザー (contoso) @msn の形式であることを確認し、ルーティングする必要があります。 これらの新しい設定では、NameDecorationRoutingDomain (NameDecorationExcludedDomainList のドメインが含まれていない場合は、「Skype コンタクトを追加」ダイアログボックスで、「Skype コンタクトを追加」ダイアログボックスで、「msn.com」に設定する必要があります)。現時点では、msn.com、live.com、Hotmail.com、outlook.com) をサポートしています。 
  
3. Skype for Business クライアントから、ユーザーは Skype ユーザーを検索および追加することができます。
    
## <a name="clients-and-interoperability-matrix"></a>クライアントと相互運用性のマトリックス

次の表に、コンシューマー向け Skype の最新バージョンと Skype for Business の最新バージョンとの相互運用性のステータスを示します。
  

|**Skype クライアント**|**連絡先の追加、IM、プレゼンス、音声、ビデオ通話**|**コメント**|
|:-----|:-----|:-----|
|Skype Windows デスクトップ  <br/> |7.6 以降、Windows XP 以降  <br/> |**新**機能: windows XP および windows Vista で実行されている windows Skype クライアント用のサポートが追加されました **(最新のクライアントバージョン7.26 以上が必要です)** 。 <br/> |
|Skype Mobile - Android 携帯電話およびタブレット   <br/> |6.19 以降、Android OS バージョン 4.0.3 以降を実行  <br/> |性能の高くない機種ではビデオ通話がサポートされない場合あり  <br/> |
|Skype Mobile-iOS  <br/> |6.11 以降、IOS 7 以降  <br/> |iPhone 4 以前、iPod 第 4 世代以前、iPad 第 1 世代はサポート外  <br/> |
|Skype Mac  <br/> |7.19 以降、Mac OS X 10.9 (Mavericks) 以降  <br/> |Mac OS X 10.9 以降  <br/> |
|Skype Universal Windows アプリ (Windows 10) デスクトップおよびモバイル  <br/> |Windows 10 (Redstone 1 更新プログラム以降)  <br/> |Windows Universal App には 2016 年秋にアップデートが配信され、相互運用性のサポートが追加される予定  <br/> |
   
次の表に、Skype for Business の最新バージョンとコンシューマー向け Skype の最新バージョンとの相互運用性のステータスを示します。 
  
|**クライアント**|**Skype Directory Search と、連絡先の追加**|**Skype A/V、IM の相互運用性**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |はい  <br/> |あり  <br/> |
|Mac 版 Skype for Business  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Desktop 2013  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Web App - オンラインとオンプレミス  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Mobile - Windows Phone  <br/> |準備中  <br/> |はい  <br/> |
|Lync Mobile - Android  <br/> |準備中  <br/> |はい  <br/> |
|Lync Mobile - iOS  <br/> |準備中  <br/> |はい  <br/> |
|Lync Room System  <br/> |準備中  <br/> |はい  <br/> |
|Lync Modern App (Win 8.1)  <br/> |はい  <br/> |あり  <br/> |
|Lync Mac 2011  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Desktop 2010  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Phone Edition  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Attendant  <br/> |該当なし  <br/> |該当なし  <br/> |
   

