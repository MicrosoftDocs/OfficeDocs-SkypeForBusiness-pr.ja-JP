---
title: Skype for Business Server に Skype の接続を展開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '概要: skype for Business Server を Skype コンシューマーと接続する方法について説明します。 これは、Skype 接続とも呼ばれます。'
ms.openlocfilehash: 1f03b873299828dedf6c0ffca113d60d277bf65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302832"
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
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server"></a>Skype for business server のパブリック IM 接続プロビジョニングサイトへのアクセス

このプロビジョニング プロセスは、完了するまで最長で 30 日かかる可能性がありますが、要求量によっては数日のみで完了することもあります。Microsoft は、このドキュメントの残りの手順を完了する前に、このプロセスを先に開始することをお勧めします。Skype のプロビジョニング プロセスが完了した後、アカウントがアクティブになり、適格なユーザーのパブリック IM 接続が有効になります。 
  
Skype Connectivity をプロビジョニングするには、次の情報が必要です。
  
- Microsoft 契約番号
    
- アクセス エッジ サービスの完全修飾ドメイン名 (FQDN)
    
- セッション開始プロトコル (SIP) のドメイン
    
- 追加のアクセス エッジ サービスの FQDN
    
- 連絡先情報
    
Skype Connectivity のプロビジョニング プロセスを開始するには、次の手順に従います。
  
1. Microsoft Windows Live ID を使用https://pic.lync.comして、web サイトにサインインします。
    
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
> PIC フェデレーションは、Live Communication Server 2005 SP1 または Office Communications Server 2007 ではサポートされなくなりました。 PIC フェデレーションでサポートされているプラットフォームには、Skype for Business Server、Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2 があります。 
  
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
    
   - IconURL: Lync &amp; Skype for business クライアントが skype の連絡先を視覚的に識別するために使用するアイコン
    
   - NameDecorationRoutingDomain と NameDecorationExcludedDomainList: setting を設定すると、ユーザーは "msn.com" で、Microsoft 以外のドメインを "装飾" していることを知らなくても、Skype ユーザーの MSAs を入力することができます。 これにより、ExcludedDomainList にないすべてのドメインに対して「user (contoso) @msn」と入力する必要がなくなります。 ドメインが除外リストに存在しない場合、SfB クライアントは自動的に MSA を書式設定します。 最も一般的な Microsoft アカウントドメインを除外リストに追加しました。
    
     > [!NOTE]
     > 変更が行われた場合は、パブリック プロバイダーを削除して新しく追加する必要があります。 インプレースでの変更は許可されていません。 
  
     > [!NOTE]
     > Lync Server 2013 CU5 以降&amp; lync デスクトップクライアントに OFFICE 2013 SP1 で追加されました。 lync ユーザーが Skype の連絡先を追加して、Microsoft 以外のドメインを「修飾」することができるようになりました。 NameDecorationRoutingDomain と NameDecorationExcludedDomainListSkype (: user (contoso) @msn の形式) を特定して、ルーティングします。 これらの新しい設定では、NameDecorationRoutingDomain (NameDecorationExcludedDomainList のドメインが含まれていない場合は、「Skype コンタクトを追加」ダイアログボックスで、「Skype コンタクトを追加」ダイアログボックスで、「msn.com」に設定する必要があります)。現時点では、msn.com、live.com、Hotmail.com、outlook.com) をサポートしています。 
  
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
|Skype for Business  <br/> |はい  <br/> |はい  <br/> |
|Mac 版 Skype for Business  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Desktop 2013  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Web App - オンラインとオンプレミス  <br/> |N/A  <br/> |N/A  <br/> |
|Lync Mobile - Windows Phone  <br/> |準備中  <br/> |はい  <br/> |
|Lync Mobile - Android  <br/> |準備中  <br/> |はい  <br/> |
|Lync Mobile - iOS  <br/> |準備中  <br/> |はい  <br/> |
|Lync Room System  <br/> |準備中  <br/> |はい  <br/> |
|Lync Modern App (Win 8.1)  <br/> |はい  <br/> |はい  <br/> |
|Lync Mac 2011  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Desktop 2010  <br/> |追加可能 (検索不可)  <br/> |はい  <br/> |
|Lync Phone Edition  <br/> |N/A  <br/> |N/A  <br/> |
|Lync Attendant  <br/> |該当なし  <br/> |該当なし  <br/> |
   

