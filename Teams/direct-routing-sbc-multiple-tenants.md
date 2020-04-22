---
title: セッション境界のコントローラーを構成する-複数のテナント
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 1つのセッション境界コントローラー (SBC) を複数のテナントに対応するように構成する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1419a42a6affa00bbeed35d328f91331ad5357ec
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779573"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントにセッション ボーダー コントローラーを構成する

ダイレクトルーティングでは、1つのセッション境界コントローラー (SBC) で複数のテナントに対応するように構成することができます。

> [!NOTE]
> このシナリオは、このドキュメントで後述する「配送業者」と呼ばれる Microsoft パートナーや PSTN キャリア向けに設計されています。 通信事業者は、Microsoft Teams に配信されたテレフォニーサービスを顧客に販売します。 

電話会社:
- データセンターで SBC を展開して管理します (顧客は SBC を実装する必要はありません。また、ユーザーは、チームクライアントの電話会社からテレフォニーサービスを受け取ります)。
- SBC と複数のテナントを相互接続します。
- ユーザーに PSTN サービスを提供します。
- 通話品質の終了を管理します。
- PSTN サービスに対して別途料金がかかります。

Microsoft は、配送業者を管理しません。 Microsoft は、PBX (Microsoft 電話システム) と Teams クライアントを提供しています。 Microsoft では、電話を認定しています。また、Microsoft 電話システムでも使用できる認定されています。 キャリアを選択する前に、お客様の選択内容が認定された SBC であり、音声品質のエンドツーエンドを管理できることを確認してください。

次に、シナリオを構成するための技術的な実装手順を示します。

**電話会社のみ:**
1. 認定された[sbc ベンダーからの指示](#deploy-and-configure-the-sbc)に従って、sbc を展開してホスティングシナリオ用に構成します。
2. キャリアテナントにベースドメイン名を登録して、ワイルドカード証明書を要求します。
3. ベースドメインの一部であるすべてのユーザーに対してサブドメインを登録します。

**顧客のグローバル管理者がいる電話会社:**
1. 顧客テナントにサブドメイン名を追加します。
2. サブドメイン名を有効にします。
3. 電話会社から顧客テナントにトランクを構成し、ユーザーをプロビジョニングします。

*DNS の基礎と、Office 365 でのドメイン名の管理について理解していることを確認してください。先に進む前に[、「Office 365 ドメインに関するヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*

## <a name="deploy-and-configure-the-sbc"></a>SBC の展開と構成

SBC ホスティングシナリオでの SBCs の展開と構成の詳細な手順については、SBC ベンダーのマニュアルを参照してください。

- **Audiocodes:** [ダイレクトルーティング構成のメモ](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)「Audiocodes の sbc から Microsoft Teams へのダイレクトルーティングホスティングモデル構成のメモ」で説明したように、sbc ホスティングシナリオの構成を確認します。 
- **Oracle:** [直接ルーティング構成のメモ](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)「Microsoft」セクションでは、SBC ホスティングシナリオの構成について説明します。 
- **リボンの通信:** リボンについては、「リボンの主要な一連の製品を構成する方法」および「このページのリボンを構成する[」](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)を参照してください。[ベストプラクティス-Microsoft Teams のダイレクトルーティング Sbc エッジの配送業者の構成](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)
- **TE システム (anynode):** 複数のテナントに対して、任意のノードの SBC を構成する方法のドキュメントと例については、[ [TE システムのコミュニティ] ページ](https://community.te-systems.de/)で登録してください。

> [!NOTE]
> 「コンタクト」ヘッダーの設定方法に注意してください。 連絡先ヘッダーは、着信招待メッセージで顧客テナントを検索するために使用されます。 

## <a name="register-a-base-domain-and-subdomains"></a>ベースドメインとサブドメインを登録する

ホスティングシナリオでは、次のものを作成する必要があります。
- 通信事業者によって所有される1つのベースドメイン名。
- すべての顧客テナントのベースドメイン名の一部であるサブドメイン。

次の例では、次のようになります。
- Adatum は、インターネットとテレフォニーサービスを提供することによって、複数の顧客に提供する電話会社です。
- Woodgrove Bank、Contoso、Adventure Works は、Office 365 ドメインを所有しているが、Adatum からテレフォニーサービスを受け取る3人のユーザーです。

サブドメインは、ユーザーに対して構成されるトランクの FQDN 名と、招待状を Office 365 に送信するときに連絡先ヘッダー内の FQDN に一致させる**必要があり**ます。 

電話が Office 365 ダイレクトルーティングインターフェイスに到着すると、インターフェイスは連絡先ヘッダーを使って、ユーザーを検索する必要があるテナントを見つけます。 直接ルーティングでは、ユーザーによっては、複数のテナントで重複する可能性のある電話番号がない可能性があるため、招待で電話番号の参照は使用されません。 そのため、連絡先ヘッダーの FQDN 名は、電話番号によってユーザーを検索する正確なテナントを特定する必要があります。

*Office 365 組織でのドメイン名の作成について詳しくは、「 [office 365 ドメインに関するヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)」を参照してください。*

次の図は、ベースドメイン、サブドメイン、連絡先ヘッダーの要件をまとめたものです。

![ドメインと連絡先ヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

SBC は、接続を認証するために証明書を必要とします。 SBC ホスティングシナリオでは、通信事業者は、 * \*base_domain (たとえば、 \*customers.adatum.biz)* で証明書を要求する必要があります。 この証明書を使って、1つの SBC から提供されている複数のテナントへの接続を認証することができます。


次の表は、1つの構成の例です。


|新しいドメイン名 |種類|登録  |SBC 用証明書 SAN  |テナントの既定のドメインの例  |ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに提示する必要がある FQDN 名|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    技術     |     運送業者のテナント  |    \*customers.adatum.biz  |   adatum.biz      |NA、これはサービステナントであり、ユーザーは存在しません |
|sbc1.customers.adatum.biz|    プロトコル  |    顧客テナントの場合  |    \*customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   プロトコル | 顧客テナントの場合   |   \*customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   プロトコル | 顧客テナントの場合 |   \*customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

基本とサブドメインを構成するには、次に説明する手順に従ってください。 この例では、1つの顧客のベースドメイン名 (customers.adatum.biz) とサブドメイン (Woodgrove Bank テナントの sbc1.customers.adatum.biz) を構成します。

> [!NOTE]
> SbcX.customers.adatum.biz を使用して、キャリアテナントの音声を有効にします。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>会社のテナントにベースドメイン名を登録する

**これらの操作は、キャリアテナントで実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>電話会社のテナントで適切な権利を持っていることを確認する

新しいドメインを追加するには、グローバル管理者として Microsoft 365 管理センターにサインインしている必要があります。 

所有しhttps://portal.office.com)ている役割を検証するには、Microsoft 365 管理センターにサインインして、[**ユーザー** > の**アクティブな**ユーザー] に移動して、グローバル管理者の役割を持っていることを確認します。 

管理者の役割と、Office 365 での役割の割り当て方法の詳細については、「 [office 365 管理者ロールについ](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>ベースドメインをテナントに追加して確認する

1.    Microsoft 365 管理センターで、[**セットアップ** > **Domains** > ドメインの**追加**] に移動します。
2.    [**自分が所有しているドメインを入力して**ください] ボックスに、ベースドメインの FQDN を入力します。 次の例では、ベースドメインは*customers.adatum.biz*です。

    ![[ドメインの追加] ページを示すスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. **[次へ]** をクリックします。
4. この例では、テナントは既に確認済みドメイン名として adatum.biz されています。 Customers.adatum.biz は既に登録されている名前のサブドメインであるため、追加の確認を求められることはありません。 ただし、以前に確認されていない FQDN を追加する場合は、確認プロセスを行う必要があります。 確認プロセスについては、[以下で説明](#add-a-subdomain-to-the-customer-tenant-and-verify-it)します。

    ![確認済みドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5.    [**次へ**] をクリックし、[ **Dns 設定の更新**] ページで [**自分で dns レコードを追加する**] を選択し、[**次へ**] をクリックします。
6.    次のページで、すべての値を削除します (Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用する場合を除く)、[**次へ**] をクリックし、[**完了**] をクリックします。 新しいドメインがセットアップの完了状態になっていることを確認します。

    ![セットアップの状態が完了しているドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>ドメイン名を有効にする

ドメイン名を登録したら、少なくとも1つの E1、E3、または E5 のライセンスを持つユーザーを追加し、作成されたベースドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てることによって、そのドメイン名をアクティブ化する必要があります。 

*Office 365 組織でのユーザーの追加の詳細については、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*

例: test@customers.adatum.biz

![[Base domain activation] ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>顧客テナントにサブドメイン名を登録する

すべてのユーザーに対して一意のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名 woodgrovebank.us を使用して、テナントにサブドメイン sbc1.customers.adatum.biz を作成します。

**以下のすべてのアクションが顧客のテナントにあります。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>お客様のテナントに適切な権限があることを確認する

新しいドメインを追加するには、グローバル管理者として Microsoft 365 管理センターにサインインしている必要があります。 

所有しhttps://portal.office.com)ている役割を検証するには、Microsoft 365 管理センターにサインインして、[**ユーザー** > の**アクティブな**ユーザー] に移動して、グローバル管理者の役割を持っていることを確認します。 

管理者の役割と、Office 365 での役割の割り当て方法の詳細については、「 [office 365 管理者ロールについ](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)て」を参照してください。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>サブドメインを顧客テナントに追加して確認する
1. Microsoft 365 管理センターで、[**セットアップ** > **Domains** > ドメインの**追加**] に移動します。
2. [**自分が所有しているドメインを入力してください**] ボックスに、このテナントのサブドメインの FQDN を入力します。 次の例では、サブドメインは sbc1.customers.adatum.biz です。

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. **[次へ]** をクリックします。
4. FQDN がテナントに登録されていない。 次の手順では、ドメインを確認する必要があります。 [**代わりに TXT レコードを追加する**] を選びます。 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. [**次へ**] をクリックして、ドメイン名を確認するために生成された TXT 値を書き留めます。

    ![[ドメインの確認] ページのテキストレコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. キャリアの DNS ホスティングプロバイダーで、前の手順の値を使用して TXT レコードを作成します。

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    詳細については、「 [Office 365 の任意の dns ホスティングプロバイダーで dns レコードを作成](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)する」を参照してください。

7. 顧客の Microsoft 365 管理センターに戻り、[**確認**] をクリックします。 
8. 次のページで、[**自分で DNS レコードを追加**します] を選択し、[**次へ**] をクリックします。

    ![[DNS 設定の更新] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. [**オンラインサービスの選択**] ページで、すべてのオプションをオフにし、[**次へ**] をクリックします。

    ![[オンラインサービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. [ **DNS 設定の更新**] ページで [**完了**] をクリックします。

    ![[DNS 設定の更新] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. ステータスが [**セットアップ完了完了**しています。 
    
    ![セットアップ完了の状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>サブドメイン名を有効にする

ドメイン名を登録したら、少なくとも1人のユーザーを追加して、sip アドレスの FQDN 部分を使用して、顧客テナント内で作成されたサブドメインと一致する SIP アドレスを割り当てることで、ライセンス認証を行う必要があります。

*Office 365 組織でのユーザーの追加の詳細については、「 [office 365 ドメインでヘルプを表示](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)する」を参照してください。*

例: test@sbc1.customers.adatum.biz

![[サブドメイン] ページのアクティブ化のスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクを作成してユーザーをプロビジョニングする

Microsoft は、直接ルーティングの最初のリリースで、新しい-CSOnlinePSTNGateway を使用して、提供される各テナント (顧客テナント) にトランクを追加する必要がありました。

ただし、これは次の2つの理由により最適とは言えません。
 
- **オーバーヘッド管理**。 たとえば、SBC のオフロードまたはドレインは、メディアのバイパスを有効または無効にするなど、いくつかのパラメーターを変更します。 ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実際には同じ SBC になります。 

-  **オーバーヘッド処理**。 複数の論理 trunks から収集されたトランクの正常性データの収集と監視 (実際には同じ SBC と物理的なトランク) によって、ルーティングデータの処理が遅くなります。
 
このフィードバックに基づいて、Microsoft は、お客様のテナントのために trunks をプロビジョニングするための新しいロジックを導入しています。

2つの新しいエンティティが導入されました。
-    CSOnlinePSTNGateway を使って、キャリアテナントに登録されているキャリアトランク。たとえば、CSOnlinePSTNGateway 5068-customers.adatum.biz-SIPSignalingport-ForwardPAI $true。

-    登録を必要としない派生トランク。 これは、単に、キャリアトランクから追加された目的のホスト名です。 これは、すべての構成パラメーターをキャリアトランクから導出します。 派生した樹幹は、PowerShell で作成する必要はありません。また、carrier トランクとの関連付けは FQDN 名に基づいています (以下の詳細を参照してください)。

**プロビジョニングロジックと例**

-    通信事業者は、CSOnlinePSTNGateway コマンドを使用して、1つのトランク (キャリアドメインのキャリアトランク) を設定して管理する必要があります。 上の例では、adatum.biz が使用されています。
-    顧客テナントでは、キャリアでは、ユーザーのボイスルーティングポリシーに派生トランク FQDN を追加するだけです。 トランクの新規 CSOnlinePSTNGateway を実行する必要はありません。
-     派生した樹幹は、名前が示すように、キャリアトランクからすべての構成パラメーターを継承または導出します。 たとえば
-    Customers.adatum.biz –航空会社のテナントに作成する必要があるキャリアトランク。
-    Sbc1.customers.adatum.biz –顧客テナントの派生トランクで、PowerShell で作成する必要はありません。  オンラインボイスルーティングポリシーの顧客テナントに派生トランクの名前を追加することはできません。
-   通信事業者は、派生した樹幹 FQDN をキャリアの SBC ip アドレスに解決する DNS レコードを設定する必要があります。

-    電話会社のトランク (キャリアテナント) で行った変更は、派生した trunks に自動的に適用されます。 たとえば、運送業者は、電話会社のトランクの SIP ポートを変更することができます。この変更は、すべての派生 trunks に適用されます。 Trunks を構成するための新しいロジックにより、すべてのテナントに移動したり、すべてのトランクのパラメーターを変更したりする必要がないため、管理が簡単になります。
-    オプションは、キャリアトランク FQDN にのみ送信されます。 キャリアトランクの正常性状態は、すべての派生 trunks に適用され、ルーティング決定に使用されます。 [ダイレクトルーティングオプション](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)の詳細については、こちらを参照してください。
-    通信事業者は、電話会社のトランクを放電することができ、派生した trunks もすべてドレインされます。 
 

**以前のモデルからキャリアトランクへの移行**
 
キャリアでホストされているモデルの現在の実装から新しいモデルに移行するには、運送業者は trunks を顧客テナント用に再構成する必要があります。 Trunks を使用して、ユーザーテナントから CSOnlinePSTNGateway を削除します (キャリアテナントにトランクを残します)。

新しいソリューションへの移行はできるだけ早くお勧めします。これにより、通信事業者と派生したトランクモデルを使用した監視とプロビジョニングが強化されます。
 

連絡先ヘッダーでサブドメインの FQDN 名の送信を構成する方法については、「 [SBC ベンダーの手順](#deploy-and-configure-the-sbc)」を参照してください。

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Muti-テナントのフェールオーバーのセットアップに関する考慮事項 

マルチテナント環境のフェールオーバーを設定するには、次の手順を実行する必要があります。

- テナントごとに、2つの異なる SBCs の Fqdn を追加します。  次に例を示します。

   customer1.sbc1.contoso.com <br>
   customer2.sbc2.contoso.com <br>

- ユーザーのオンライン音声ルーティングポリシーで、SBCs の両方を指定します。  1つの SBC で障害が発生した場合、ルーティングポリシーによって2番目の SBC に通話がルーティングされます。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)

