---
title: Skype for Business Server 2015 での Skype 接続の展開
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: は、Skype をビジネス サーバー 2015 の Skype のコンシューマーに接続する方法を説明します。 これは、Skype 接続とも呼ばれます。'
ms.openlocfilehash: 4d81d2529435d250957c775d954a33a562bed1e9
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569167"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での Skype 接続の展開
 
**概要:** Skype for Business Server 2015 と、Skype コンシューマー向け製品を接続する方法について説明します。これは、Skype 接続とも呼ばれます。
  
ここでは、Skype Connectivity の展開について順を追って説明します。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Connectivity の概要 (IT 担当者向け)

Skype 接続では、検索し、Skype ユーザーを追加する機能により、ビジネス ユーザー向け Skype を提供します。 Skype の接続は、Skype ユーザーとフェデレーションおよびディレクトリの検索を有効にすることができるビジネスの Skype の機能です。 Skype の接続を有効にした後、ビジネス ユーザー向けに、Skype は検索し、Skype ユーザーを追加することになります。
  
## <a name="skype-directory-search"></a>Skype Directory Search

Skype Directory Search 機能によって、Skype for Business ユーザーは、Skype の連絡先を検索できます。検索機能により、ユーザーは以下の手段を使用して検索を実行できます。
  
- **"John Doe"の例の表示名で検索**を探しているものが見つからなかったため、多くの結果を返すこの可能性があります。
    
- **表示名と場所、「John Doe のバルセロナ」の使用例での検索**- これは絞り検索の結果かなり。
    
- **例"johndoe@outlook.com"、電子メールでの検索**- これはほとんどの場合で 1 つの結果を返す必要があります指定された電子メールを正確に一致するものです。 同じメールが複数のアカウントに関連付けられている場合は、複数の結果が返される場合があります。
    
- **例「123-123-1234」の電話番号で検索**- これはほとんどの場合で 1 つの結果を返す必要があります指定された電話を正確に一致するものです。 電話番号は、国コード (つまり 1-xxx、yyy-zzzz) を含める必要があります。 同じ電話番号が複数のアカウントに関連付けられている場合は、複数の結果が返される場合があります。
    
- **Skype 名を「JohnDoe1456」の使用例で検索**の正確な一致が見つかった場合、それが結果として返される、最初。 他の"name"の一致候補が返されます。
    
    > [!NOTE]
    > Skype Directory Search では、ポート 443 で IP アドレス 104.40.75.246、23.101.135.34、40.113.86.19 と通信できる必要があります。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype Directory Search のサポートされる展開のマトリックス

以下の表に、Skype Directory Search のサポートの概要を示します。
  

||**ビジネス 2015 のサーバーのフロント エンドの Skype**|**Lync Server 2013 (または古い) フロント エンド**|**コメント**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server 2015 エッジ  <br/> |サポート対象  <br/> |サポート対象外  <br/> |Skype for Business Server 2015 およびエッジは Skype Directory Search に必須  <br/> |
|サイド バイ サイドで展開されている Skype for Business Server 2015 エッジ + Lync Server 2013 エッジ  <br/> |サポート対象  <br/> |サポート対象外  <br/> |Skype Directory Search のトラフィックは Skype for Business Server エッジ サーバーを通過します。フェデレーション トラフィックは、管理者により構成されたエッジを通過します。たとえば、管理者は、Skype Directory Search をサポートしない Lync Server 2013 エッジ サーバーを介してフェデレーション トラフィックを引き続き送信することを選択できます。  <br/> |
|Lync Server 2013 (またはそれ以降の) エッジ  <br/> |サポート対象外  <br/> |サポート対象外  <br/> ||
   
> [!NOTE]
> Skype for Business Server 2015 フロントエンドで実行されているアドレス帳サービスは、2015 エッジ サーバーの Skype 検索ポート 4443 の存在により、2015 エッジを検出します。 
  
> [!NOTE]
> オンプレミス展開に複数のサイトがあるカスタマーの場合、Skype for Business Server 2015 エッジ サーバー/プールを 1 つだけ展開していると、すべてのサイトから着信する検索トラフィックは、利用できる単一のエッジ サーバーを通過します。管理者は、すべてのサイトのプールが、展開済みの Skype for Business Server 2015 エッジ サーバー/プールにアクセスできることを確認する必要があります。 
  
> [!NOTE]
> Skype グラフ サービスは、要求レートが 15 要求/秒を超えた場合、すべてのオンプレミスまたは Office 365 カスタマーからの検索要求を調整します。 
  
> [!NOTE]
> 大規模エンタープライズ オンプレミス カスタマーに対しては、より高い要求レートを許可するために、ドメインを Skype 検索サービスのホワイトリストに登録する必要があります。 
  
> [!NOTE]
> キューに保留中である要求の数が多すぎる場合、Skype for Business Server 2015 は、着信要求を調整します。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Office 365 での Skype for Business Server Online 用の Skype Connectivity の展開

Skype Connectivity は、Office 365 の一部である Skype for Business Online の機能でもあります。Office 365 ポータル内の Skype for Business 管理センターから、Skype Connectivity 機能を有効にすることができます。
  
Office 365 の中規模ビジネス、Office 365 のエンタープライズ、Office 365 の教育、および政府の Office 365 の: office 365 ポータルにサインインし、ビジネス管理センターの Skype に移動します。 外部との連絡に移動します。 パブリック IM サービス プロバイダーでは、[有効] をクリックします。 Skype 接続する個々 のユーザーのアクセスを制御する場合は、これを行う個々 のユーザーの外部通信の設定を編集します。
  
小規模のビジネス プレミアム: Office 365 用には、Office 365 にサインインし、管理者には、\>サービスの設定\>インスタント メッセージング、会議および会議。 外部との連絡を入れます。 外部との連絡のスイッチは、Skype の接続性とビジネスの Skype を使用する他の組織との通信の両方オンにします。
  
Skype for Business Online の管理の詳細については、次の記事を参照してください。
  
- [外部の Skype のビジネスまたは Skype の連絡先と通信ビジネスのオンライン ユーザーの Skype を使用します。](https://support.office.com/en-us/article/Let-Skype-for-Business-Online-users-communicate-with-external-Lync-or-Skype-contacts-b414873a-0059-4cd5-aea1-e5d0857dbc94?ui=en-US&amp;rs=en-US&amp;ad=US )
    
- [[中小企業] 組織の外部と通信ビジネスのオンライン ユーザーの Skype を使用します。](https://support.office.com/en-US/article/Let-Lync-Online-users-communicate-outside-your-organization-Small-Business-7F488F09-F004-4DB5-AEC5-01C262AA3D34)
    
- [ビジネスまたは Skype の外部の連絡先の IM の Skype することはできないときにどのような](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [ビジネス用の Skype を使用して、外部の連絡先に接続するには](https://support.office.com/en-US/article/Use-Lync-to-connect-with-external-contacts-E6DA21CE-FFB8-4AF3-A171-871CA245BC30)
    
- [ビジネス用の Skype の連絡先を追加します。](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
    
- [個々 のユーザー用の設定を管理します。](https://support.office.com/en-US/article/Configure-settings-for-individual-users-77B26EAC-8228-4161-BA9F-733B187BD836)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 用の Skype Connectivity の展開

ビジネス サーバー 2015 の Skype は、Skype との接続をサポートするためにフェデレーション アクセス アーキテクチャを使用します。 この接続では、Skype は、Skype を追加するのにはビジネスのサーバーのユーザーが有効にします。 Skype クライアントは Skype を連絡先リストにビジネス ・ ユーザーの追加もできます。 ビジネス サーバーのユーザーがインスタント メッセージングを使用して通信できるの Skype で管理者によって設定されたポリシーに基づき、互いの存在を参照してくださいし、音声通話とビデオ通話を開始します。 Skype の接続も、有効にできる Skype、Skype からのオンライン ビジネスのお客様のビジネス管理センターの Office 365 ポータル内のビジネス オンラインでは、Skype の機能です。
  
> [!NOTE]
> Skype for Business Server がパブリック インスタント メッセージング接続 (PIC) を使用して Windows Messenger と接続するように既に構成されている場合、展開は、既に Skype Connectivity 用に構成されています。検討が必要と思われるのは、既存の Messenger PIC エントリの名前を Skype などに変更することだけです。 
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server-2015"></a>Skype for Business Server 2015 から Skype for Business Server のパブリック IM 接続プロビジョニング サイトへのアクセス

このプロビジョニング プロセスは、完了するまで最長で 30 日かかる可能性がありますが、要求量によっては数日のみで完了することもあります。Microsoft は、このドキュメントの残りの手順を完了する前に、このプロセスを先に開始することをお勧めします。Skype のプロビジョニング プロセスが完了した後、アカウントがアクティブになり、適格なユーザーのパブリック IM 接続が有効になります。 
  
Skype Connectivity をプロビジョニングするには、次の情報が必要です。
  
- Microsoft 契約番号
    
- アクセス エッジ サービスの完全修飾ドメイン名 (FQDN)
    
- セッション開始プロトコル (SIP) のドメイン
    
- 追加のアクセス エッジ サービスの FQDN
    
- 連絡先情報
    
Skype Connectivity のプロビジョニング プロセスを開始するには、次の手順に従います。
  
1. Web サイトにサインインするのにhttps://pic.lync.comを Microsoft Windows Live ID を使用して
    
2. Microsoft ライセンスの契約の種類を選びます。
    
3. チェック ボックスをオンにし、Skype for Business Server の製品使用権の内容を読んで同意したことを確認します。
    
4. プロビジョニング要求を開始するためのページで、適切なリンクをクリックしてプロビジョニング要求を開始します。
    
5. プロビジョニング情報を指定するためのページで、アクセス エッジ サービスの FQDN を入力します。 たとえば、sip.contoso.com と入力します。
    
    > [!IMPORTANT]
    > 2017 年 7 月 1 日以降マイクロソフトは、パブリック インスタント メッセージの接続を機能し続けるために、お客様側でのフェデレーション DNS SRV レコードの展開を追加の必須要件とします。 
  
6. 少なくとも 1 つの SIP ドメイン名を入力し、[追加] をクリックします。
    
    > [!NOTE]
    > プロビジョニング プロセスを完了するには、少なくとも 1 つのアクセス エッジ サーバーが必要です。1 つのアクセス エッジ FQDN で複数の SIP ドメインをサポートできますが、複数のアクセス エッジ FQDN で 1 つの SIP ドメインを表現することはできません。SIP ドメインとアクセス エッジ サーバーは、アクティブで、正常に機能し、ネットワーク上で到達可能である必要があります。 
  
7. [パブリック IM サービス プロバイダー] の一覧で [Skype] を選び、[次へ] をクリックして連絡先情報を追加し、プロビジョニング要求を送信します。
    
プロビジョニング要求が送信された後、アカウントをアクティブにして、ユーザーを Skype Connectivity で有効にするには、最長 30 日かかる可能性があります。ただし、キューによっては数日のみで済むこともあります。
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a>フェデレーションとパブリック IM 接続 (PIC) の有効化

プロビジョニング要求を送信した後は、Skype Connectivity を構成するために必要な、Skype for Business Server の環境と管理タスクに重点を移すことができます。このセクションでは、管理者は Skype for Business Server を展開し、外部アクセス (エッジ サーバーとも呼ばれます) を構成していることを前提としています。 
  
フェデレーションと PIC を有効にするために必要な主な 3 つのステップは次のとおりです。
  
1. フェデレーションと PIC を構成する
    
2. フェデレーション ユーザーのアクセスをサポートするように、少なくとも 1 つのポリシーを構成する
    
3. Skype PIC プロバイダー設定を構成する
    
#### <a name="1-configure-federation-and-pic"></a>1. フェデレーションと PIC を構成する

フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、Skype for Business Server コントロール パネルを使用して構成します。
  
> [!NOTE]
> PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。PIC フェデレーションがサポートされるプラットフォームとしては、Skype for Business Server 2015、Lync Server 2013、Lync Server 2010、および Office Communications Server 2007 R2 があります。 
  
フェデレーションは、Skype ユーザーが組織内の Skype for Business ユーザーと通信できるようにするために必要です。パブリック インスタント メッセージング接続 (PIC) はフェデレーションの 1 つのクラスで、また PIC を構成して Skype for Business ユーザーが Skype ユーザーと通信できるようにする必要があります。フェデレーションと PIC は、次に示すように Skype for Business Server コントロール パネルの [エッジ構成] ダイアログを使用して構成します。
  
![新しいエッジ プールの定義](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 検索を使用するには、パブリック プロバイダーの設定 (後の手順を参照) で EnableSkypeIdRouting 属性と EnableSkypeDirectorySearch 属性を True に設定する必要があります。 
  
これで、サーバー上で実行する必要がある管理タスクが完了し、Skype Connectivity を使用するように設定されました。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. フェデレーション ユーザー アクセスをサポートするために少なくとも 1 つのポリシーを構成します。

管理者は Skype for Business Server コントロール パネルを使用して外部ユーザー アクセス ポリシーを 1 つ以上構成し、Skype ユーザーが内部の Skype for Business Server ユーザーと共同作業できるかどうかを制御する必要があります。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 設定 Skype PIC プロバイダーを構成します。

管理者は Skype for Business Server 管理シェルを使用して Skype for Business クライアント ポリシーを構成し、Skype を追加の PIC プロバイダーとして表示する必要があります。 
  
> [!NOTE]
> パブリック インスタント メッセージング接続 (PIC) サービス プロバイダーのユーザーは、パブリック IM 接続をサポートするためにも少なくとも 1 つのポリシー (この手順で前の手順 2) を構成するまで、IM または組織内の会議に参加できません。 
  
新規インストールの場合は、図に示すように Skype for Business Server コントロール パネルを使用して Skype パブリック プロバイダーを有効にすることで、Skype Connectivity を構成することができます。
  
![SIP フェデレーション プロバイダー](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Skype for Business Server にアップグレードする場合に Skype Connectivity を構成するには、既存の Skype パブリック プロバイダーを削除してから再度追加する必要があります。 
  
Skype Connectivity の構成は、PowerShell のみを使用して行うこともできます。PowerShell を使用して Skype Connectivity を構成するには、次の手順に従います。
  
1. Skype for Business Server フロントエンド サーバーから、Skype for Business Server 管理シェルを開きます。
    
2. 次の 2 つのコマンドを実行します。
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 環境にまだ PIC プロバイダーがなく、新しい PIC プロバイダーを作成している場合は、Remove-CsPublicProvider コマンドレットを実行する必要はありません。 
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    意味がわかりにくいパラメーターの動作
    
  - ProxyFqdn:  (Microsoft により所有/維持管理される) Skype フェデレーション エッジの場所
    
  - IconURL: アイコンが Lync で使用される&amp;Skype 連絡先を視覚的に識別するビジネスの Skype
    
  - NameDecorationRoutingDomain および NameDecorationExcludedDomainList:「msn.com」でマイクロソフト以外のドメインを「装飾」について理解することがなく Skype ユーザーの MSAs を入力するユーザーは、これらの設定。 ExcludedDomainList ではないすべてのドメインの"ユーザー (contoso.com) @msn.com"を入力する必要があります。 ドメインが除外リストに存在しない場合、SfB クライアントは自動的に MSA を書式設定します。 最も一般的な Microsoft アカウント ドメインから除外する一覧に追加しました。
    
    > [!NOTE]
    > 変更が行われた場合は、パブリック プロバイダーを削除して新しく追加する必要があります。 インプレースでの変更は許可されていません。 
  
    > [!NOTE]
    > Lync Server 2013 CU5 に追加&amp;Office 2013 の SP1 では、NameDecorationRoutingDomain および NameDecorationExcludedDomainList でデスクトップの Lync クライアントは、Skype 連絡先を追加するに必要な Lync ユーザーを「修飾」するマイクロソフト以外のドメイン状況を改善識別し、Skype にルーティング (の形式: user(contoso.com)@msn.com)。 これらの新しい設定とアドレスのユーザーの自動書式設定の入力"Skype の連絡先の追加] ダイアログ ボックスで (これは、msn.com に設定する必要があります)、NameDecorationRoutingDomain と NameDecorationExcludedDomainList (内のドメインが含まれていない場合、します。現在サポートできます msn.com、live.com、Hotmail.com、outlook.com)。 
  
3. Skype for Business クライアントから、ユーザーは Skype ユーザーを検索および追加することができます。
    
## <a name="clients-and-interoperability-matrix"></a>クライアントと相互運用性のマトリックス

次の表に、コンシューマー向け Skype の最新バージョンと Skype for Business の最新バージョンとの相互運用性のステータスを示します。
  

|**Skype クライアント**|**取引先担当者、IM、プレゼンス、オーディオ、およびビデオ通話を追加します。**|**コメント**|
|:-----|:-----|:-----|
|Skype Windows デスクトップ  <br/> |7.6 以降、Windows XP 以降  <br/> |**新規**: Windows XP および Windows Vista で実行されている Windows の Skype クライアントのサポートが追加 * * (7.26 またはそれ以降の最新のクライアント バージョンが必要です) * * <br/> |
|Skype Mobile - Android 携帯電話およびタブレット   <br/> |6.19 以降、Android OS バージョン 4.0.3 以降を実行  <br/> |性能の高くない機種ではビデオ通話がサポートされない場合あり  <br/> |
|Skype 携帯 - iOS  <br/> |6.11 以降、IOS 7 以降  <br/> |iPhone 4 以前、iPod 第 4 世代以前、iPad 第 1 世代はサポート外  <br/> |
|Skype Mac  <br/> |7.19 以降、Mac OS X 10.9 (Mavericks) 以降  <br/> |Mac OS X 10.9 以降  <br/> |
|Skype Universal Windows アプリ (Windows 10) デスクトップおよびモバイル  <br/> |Windows 10 (Redstone 1 更新プログラム以降)  <br/> |Windows Universal App には 2016 年秋にアップデートが配信され、相互運用性のサポートが追加される予定  <br/> |
   
次の表に、Skype for Business の最新バージョンとコンシューマー向け Skype の最新バージョンとの相互運用性のステータスを示します。 
  
|**クライアント**|**Skype ディレクトリを検索し、連絡先を追加します。**|**Skype の A/V、IM の相互運用機能**|
|:-----|:-----|:-----|
|Skype for Business 2015  <br/> |はい  <br/> |あり  <br/> |
|Mac 用 Skype For Business  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Desktop 2013  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Web App - オンラインとオンプレミス  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Mobile - Windows Phone  <br/> |準備中  <br/> |はい  <br/> |
|Lync Mobile - Android  <br/> |準備中  <br/> |はい  <br/> |
|Lync Mobile - iOS  <br/> |準備中  <br/> |はい  <br/> |
|Lync Room System  <br/> |準備中  <br/> |はい  <br/> |
|Lync Modern App (Win 8.1)  <br/> |はい  <br/> |はい  <br/> |
|Lync Mac 2011  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Desktop 2010  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Phone Edition  <br/> |該当なし  <br/> |該当なし  <br/> |
|Lync Attendant  <br/> |該当なし  <br/> |該当なし  <br/> |
   

