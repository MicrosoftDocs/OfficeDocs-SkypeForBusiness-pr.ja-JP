---
title: セッション ボーダー コントローラーの構成 - 複数のテナント
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
description: 1 つのセッション ボーダー コントローラー (SBC) を構成して、Microsoft パートナーや PSTN 通信事業者に複数のテナントを提供する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ff378d55f551cfb11bd6f185840407e20095035
ms.sourcegitcommit: 272e8cf0075a566f055801433c9eb0313050530f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2021
ms.locfileid: "52486381"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントにセッション ボーダー コントローラーを構成する

ダイレクト ルーティングでは、複数のテナントにサービスを提供する 1 つのセッション ボーダー コントローラー (SBC) の構成がサポートされています。

> [!NOTE]
> このシナリオは、このドキュメントの後半で「通信事業者」と呼ばれる Microsoft パートナーや PSTN 通信事業者向けに設計されています。 運送業者は、顧客に提供されるテレフォニー Microsoft Teamsを販売します。 

運送業者:
- データセンターに SBC をデプロイして管理します (お客様は SBC を実装する必要が生じず、Teams クライアントの通信事業者からテレフォニー サービスを受け取ります)。
- SBC を複数のテナントに相互接続します。
- PSTN サービスを顧客に提供します。
- 通話品質のエンド エンド を管理します。
- PSTN サービスに対して個別に料金が発生します。

Microsoft は通信事業者を管理していない。 Microsoft では、PBX (Microsoft 電話 システム) とクラウド クライアントTeamsしています。 また、Microsoft は携帯電話を認定し、マイクロソフトのシステムで使用できる SBC Microsoft 電話します。 通信事業者を選択する前に、選択した SBC が認定され、音声品質をエンド エンド で管理できる必要があります。

シナリオを構成するための技術的な実装手順を次に示します。

**運送業者のみ:**
1. SBC をデプロイし、認定された SBC ベンダーからの指示に従ってホスティング [シナリオ用に構成します](#deploy-and-configure-the-sbc)。
2. キャリア テナントにベース ドメイン名を登録し、ワイルドカード証明書を要求します。
3. ベース ドメインの一部であるすべての顧客にサブドメインを登録します。

**顧客グローバル管理者を持つ運送業者:**
1. サブドメイン名を顧客テナントに追加します。
2. サブドメイン名をアクティブ化します。
3. 運送業者から顧客テナントへのトランクを構成し、ユーザーをプロビジョニングします。

*DNS の基本とドメイン名の管理方法については、Microsoft 365 または Office 365。さらに [進む前に、「Microsoft 365またはOffice 365ヘルプを表示する」](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*

## <a name="deploy-and-configure-the-sbc"></a>SBC のデプロイと構成

SBC ホスティング シナリオ用に SBC をデプロイおよび構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。

- **AudioCodes:** [ダイレクト ルーティング](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)構成に関するメモ 。「Direct Routing Hosting Model Configuration Note への AudioCodes SBC の接続Microsoft Teams SBC ホスティング シナリオの構成」を参照してください。 
- **Oracle:** [ダイレクト ルーティング構成に関する注意](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)。 SBC ホスティング シナリオの構成については、「Microsoft」セクションで説明しています。 
- **リボンコミュニケーション:** リボン コア シリーズの SBC を構成する方法に関するドキュメントについては、リボン通信 [SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)構成ガイドを参照してください。リボンのベスト プラクティス - Microsoft Teams Direct Routing [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)の通信事業者の構成に関するページを参照してください。
- **TE-Systems (anynode):** 複数のテナントに anynode SBC を構成する方法に関するドキュメントと例については [、TE-Systems](https://community.te-systems.de/) Community ページに登録してください。
- **Metaswitch:** 複数のテナントに [対](https://manuals.metaswitch.com/MAN39555)して Perimeta SBC を有効にする方法に関するドキュメントについては、Metaswitch Community ページに登録してください。

> [!NOTE]
> "Contact" ヘッダーを構成する方法に注意してください。 Contact ヘッダーは、受信した招待メッセージで顧客テナントを検索するために使用されます。 

## <a name="register-a-base-domain-and-subdomains"></a>ベース ドメインとサブドメインを登録する

ホスティング シナリオでは、次を作成する必要があります。
- 通信事業者が所有する 1 つのベース ドメイン名。
- すべての顧客テナントのベース ドメイン名の一部であるサブドメイン。

次の例では、
- Adatum は、インターネットおよびテレフォニー サービスを提供することで、複数の顧客にサービスを提供する通信事業者です。
- Woodgrove Bank、Contoso、Adventure Works は、Microsoft 365 または Office 365 ドメインを持ち、Adatum からテレフォニー サービスを受け取る 3 人のお客様です。

サブドメインは、顧客に対して構成されるトランクの FQDN 名と、Microsoft 365 または Office 365 への招待を送信するときに連絡先ヘッダーの FQDN と一致する必要があります。 

Microsoft 365 または Office 365 ダイレクト ルーティング インターフェイスに呼び出しが到着すると、インターフェイスは Contact ヘッダーを使用して、ユーザーを検索する必要があるテナントを検索します。 ダイレクト ルーティングでは、複数のテナントで重複する可能性がある DID 以外の番号を持つお客様もいます。招待では電話番号の参照は使用しません。 そのため、電話番号でユーザーを検索する正確なテナントを識別するには、Contact ヘッダーの FQDN 名が必要です。

*組織で [ドメイン名を作成する方法Office 365ドメイン](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)に関するヘルプを参照Microsoft 365参照Office 365してください。*

次の図は、ベース ドメイン、サブドメイン、および Contact ヘッダーの要件をまとめたものです。

![ドメインと連絡先ヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

SBC では、接続を認証するための証明書が必要です。 SBC ホスティング シナリオの場合、通信事業者は CN または .base_domain SAN 証明書 (例: *\* \* .customers.adatum.biz)* で証明書を要求する必要があります。 この証明書を使用して、1 つの SBC から提供される複数のテナントへの接続を認証できます。


次の表は、1 つの構成の例です。


|新しいドメイン名 |種類|登録済み  |SBC の証明書 CN/SAN  |この例のテナントの既定のドメイン  |ユーザーに呼び出しを送信するときに、SBC が Contact ヘッダーに表示する必要があります FQDN 名|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     運送業者テナント内  |    \*.customers.adatum.biz  |   adatum.biz      |NA、これはサービス テナント、ユーザーなし |
|sbc1.customers.adatum.biz|    サブドメイン  |    顧客テナント内  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   サブドメイン | 顧客テナント内   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   サブドメイン | 顧客テナント内 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

ベースドメインとサブドメインを構成するには、以下の手順に従ってください。 この例では、1 人の顧客 (Woodgrove Bank テナント内の sbc1.customers.adatum.biz) のベース ドメイン名 (customers.adatum.biz) とサブドメインを構成します。

> [!NOTE]
> [sbcX.customers.adatum.biz を使用して、通信事業者のテナントで音声を有効にします。 sbcX には、任意の一意の有効な英数字ホスト名を指定できます。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>キャリア テナントにベース ドメイン名を登録する

**これらのアクションは、通信事業者テナントで実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>通信事業者のテナントで適切な権限を持っている必要があります

新しいドメインは、グローバル管理者として Microsoft 365にサインインした場合にのみ追加できます。 

ロールを検証するには、Microsoft 365 管理センター ( にサインインし、[ユーザーのアクティブなユーザー] に移動し、グローバル管理者ロールが割り当て済みである https://portal.office.com)   >  必要があります。 

管理者ロールの詳細と、管理者ロールまたは管理者ロールでロールを割り当てるMicrosoft 365をOffice 365管理者ロールについてを[参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>テナントにベース ドメインを追加して確認する

1. 管理センター Microsoft 365、[ドメインの追加]**の**  >  **設定に**  >  **移動します**。
2. [所有 **するドメインを入力してください] ボックス** に、ベース ドメインの FQDN を入力します。 次の例では、ベース ドメインは *customers.adatum.biz。*

    ![[ドメインの追加] ページを示すスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. **[次へ]** をクリックします。
4. この例では、テナントは既に adatum.biz ドメイン名として使用されています。 既に登録されている名前のサブドメイン customers.adatum.biz、追加の確認は求めされません。 ただし、以前に確認されていない FQDN を追加する場合は、検証のプロセスを実行する必要があります。 検証のプロセスについては、以下 [で説明します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![確認済みのドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5. [**次へ**] をクリックし設定 DNS レコードの更新] ページで **、[** 自分で **DNS** レコードを追加する] を選択し、[次へ] を **クリックします**。
6. 次のページで、(Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用しない限り) すべての値をクリアし、[次へ] をクリックし、[完了] をクリック **します**。 新しいドメインがセットアップの完了状態にあるか確認します。

    ![セットアップが完了した状態のドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>ドメイン名をアクティブ化する

ドメイン名を登録したら、電話システム ライセンスを持つ少なくとも 1 人のユーザーを追加し、作成したベース ドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当て、ドメイン名をアクティブ化する必要があります。 ライセンスは、ドメインのライセンス認証後に取り消されます (最大 24 時間かかる場合があります)。

> [!NOTE]
> Carrier テナントは、テナントに割り当電話システム少なくとも 1 つのライセンスを保持して、構成の削除を回避Skype for Businessがあります。 

*組織での [ユーザーの追加の詳細については](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)、「Microsoft 365 または Office 365 ドメインに関するヘルプを参照Microsoft 365参照Office 365してください。*

例: test@customers.adatum.biz

![ベース ドメインのアクティブ化ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>顧客テナントにサブドメイン名を登録する

顧客ごとに一意のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名を持つ sbc1.customers.adatum.biz にサブドメイン ドメインを作成 woodgrovebank.us。

**以下のすべてのアクションは、顧客テナントに含めます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>顧客テナントで適切な権限を持っている

新しいドメインは、グローバル管理者として Microsoft 365にサインインした場合にのみ追加できます。 

ロールを検証するには、Microsoft 365 管理センター ( にサインインし、[ユーザーのアクティブなユーザー] に移動し、グローバル管理者ロールが割り当て済みである https://portal.office.com)   >  必要があります。 

管理者ロールの詳細と、管理者ロールまたは管理者ロールでロールを割り当てるMicrosoft 365をOffice 365管理者ロールについてを[参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>顧客テナントにサブドメインを追加して確認する
1. 管理センター Microsoft 365、[ドメインの追加]**の**  >  **設定に**  >  **移動します**。
2. [所有 **するドメインを入力してください** ] ボックスに、このテナントのサブドメインの FQDN を入力します。 次の例では、サブドメインが sbc1.customers.adatum.biz。

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. **[次へ]** をクリックします。
4. FQDN がテナントに登録されたことがない。 次の手順では、ドメインを確認する必要があります。 [代 **わりに TXT レコードを追加する] を選択します**。 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. [次 **へ]** をクリックし、生成された TXT 値をメモしてドメイン名を確認します。

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 通信事業者の DNS ホスティング プロバイダーで、前の手順の値を使用して TXT レコードを作成します。

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    詳細については、「任意の DNS ホスティング プロバイダー [で DNS レコードを作成する」を参照してください](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 顧客の管理センターに戻り、[確認Microsoft 365をクリック **します**。 
8. 次のページで、[自分で DNS レコードを追加する] **を選択し** 、[次へ] を **クリックします**。

    ![[DNS 設定の更新] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. [オンライン **サービスの選択] ページで、** すべてのオプションをオフにし、[次へ] を **クリックします**。

    ![[オンライン サービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. [DNS **設定の** 更新 **] ページで [完了] をクリック** します。

    ![[DNS 設定の更新] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. 状態が [セットアップ完了] **です**。 
    
    ![セットアップ完了の状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> ダイレクト ルート トランクを追加するには、個々のクライアントのベース URL とサブドメインが同じテナント上に _必要_ です。

### <a name="activate-the-subdomain-name"></a>サブドメイン名をアクティブ化する

ドメイン名を登録したら、少なくとも 1 人のユーザーを追加してアクティブ化し、顧客テナントで作成されたサブドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てる必要があります。 ライセンスは、サブドメインのアクティブ化後にユーザーから取り消されます (最大 24 時間かかる場合があります)。

*組織での [ユーザーの追加の詳細については](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)、「Microsoft 365 または Office 365 ドメインに関するヘルプを参照Microsoft 365参照Office 365してください。*

例: test@sbc1.customers.adatum.biz

![[サブドメインのアクティブ化] ページのスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクを作成してユーザーをプロビジョニングする

ダイレクト ルーティングの最初のリリースでは、Microsoft は New-CSOnlinePSTNGateway を使用して、提供される各テナント (顧客テナント) にトランクを追加する必要がありました。

ただし、これは次の 2 つの理由で最適であることが証明されません。
 
- **オーバーヘッド管理**。 たとえば、SBC をオフロードまたはドレインすると、メディア バイパスの有効化や無効化など、いくつかのパラメーターが変更されます。 ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実際には同じ SBC です。 

-  **オーバーヘッド処理**。 トランク正常性データの収集と監視 - 実際には、同じ SBC と同じ物理トランクである複数の論理トランクから収集された SIP オプションは、ルーティング データの処理を遅くします。
 
このフィードバックに基づいて、Microsoft は顧客テナントのトランクをプロビジョニングする新しいロジックを取り入れしています。

2 つの新しいエンティティが導入されました。
-    New-CSOnlinePSTNGateway コマンド (例: New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true) を使用して、キャリア テナントに登録されたキャリア トランク。

-    登録を必要としない派生トランク。 これは、単に、キャリア トランクから追加された目的のホスト名です。 このパラメーターは、すべての構成パラメーターをキャリア トランクから派生します。 派生トランクは PowerShell で作成する必要は一方で、キャリア トランクとの関連付けは FQDN 名に基づいて行います (詳細については、以下を参照してください)。

**プロビジョニング ロジックと例**

-    運送業者は、次のコマンドを使用して、単一のトランク (キャリア ドメイン内のキャリア トランク) を設定Set-CSOnlinePSTNGateway必要があります。 上記の例では、次 adatum.biz。
-    顧客テナントでは、運送業者は、派生トランク FQDN をユーザーの音声ルーティング ポリシーに追加する必要があります。 トランクに対してNew-CSOnlinePSTNGatewayする必要はありません。
-    名前が示すように、派生トランクは、すべての構成パラメーターをキャリア トランクから継承または派生します。 例:
-    Customers.adatum.biz – 運送業者テナントに作成する必要がある運送業者のトランク。
-    Sbc1.customers.adatum.biz – PowerShell で作成する必要はない、顧客テナント内の派生トランク。  顧客テナントの派生トランクの名前は、オンライン音声ルーティング ポリシーで作成せずに追加できます。
-   運送業者は、派生トランク FQDN をキャリア SBC IP アドレスに解決する DNS レコードを設定する必要があります。

-    (キャリア テナント上の) 運送業者のトランクに加えた変更は、派生トランクに自動的に適用されます。 たとえば、運送業者は、運送業者のトランクで SIP ポートを変更できます。この変更は、すべての派生トランクに適用されます。 トランクを構成する新しいロジックは、すべてのテナントに移動してすべてのトランクでパラメーターを変更する必要がなさらないので、管理を簡素化します。
-    オプションは、通信事業者のトランク FQDN にのみ送信されます。 キャリア トランクの正常性状態は、すべての派生トランクに適用され、ルーティングの決定に使用されます。 ダイレクト ルーティング オプションの [詳細については、 を参照してください](./direct-routing-monitor-and-troubleshoot.md)。
-    キャリアは、キャリアトランクをドレインできます。また、派生したトランクもすべてドレインされます。 
 
> [!NOTE]
> キャリア トランクに適用される番号変換ルールは、派生トランクには適用されません。 これは既知の問題です。 別のソリューションとして、顧客のテナントごとに数値変換ルールを作成する必要があります。

**前のモデルからキャリア トランクへの移行**
 
運送業者がホストするモデルの現在の実装から新しいモデルに移行するには、運送業者が顧客テナントのトランクを再構成する必要があります。 (運送業者のテナントにトランクを残す) Remove-CSOnlinePSTNGatewayを使用して、顧客のテナントからトランクを削除します。

運送業者と派生トランク モデルを使用して監視とプロビジョニングを強化する予定で、できるだけ早く新しいソリューションに移行することを強くお勧めします。
 

Contact ヘッダーで [サブドメインの](#deploy-and-configure-the-sbc) FQDN 名を送信する構成については、SBC ベンダーの手順を参照してください。

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>マルチテナント フェールオーバーの設定に関する考慮事項 

マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。

- テナントごとに、2 つの異なる SBC の FQDN を追加します。  次に例を示します。

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- ユーザーのオンライン音声ルーティング ポリシーで、両方の SBC を指定します。  1 つの SBC が失敗した場合、ルーティング ポリシーは 2 つ目の SBC に呼び出しをルーティングします。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
