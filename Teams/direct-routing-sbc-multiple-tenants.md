---
title: セッション ボーダー コントローラーを構成する - 複数のテナント
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
description: 1 つのセッション ボーダー コントローラー (SBC) を構成して、Microsoft パートナーや PSTN キャリア用に複数のテナントにサービスを提供する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343e2d1aedefd34de452df8da6ce9a5ad1a726ba
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923849"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントにセッション ボーダー コントローラーを構成する

ダイレクト ルーティングでは、複数のテナントにサービスを提供する 1 つのセッション ボーダー コントローラー (SBC) の構成がサポートされています。

> [!NOTE]
> このシナリオは、このドキュメントの後半で通信事業者と呼ばれる、Microsoft パートナーや PSTN 通信事業者向けに設計されています。 通信事業者は、Microsoft Teams に配信されたテレフォニー サービスを顧客に販売しています。 

通信事業者:
- データセンターに SBC を展開して管理します (お客様は SBC を実装する必要は不要で、Teams クライアントの通信事業者からテレフォニー サービスを受け取ります)。
- SBC を複数のテナントに相互接続します。
- PSTN サービスをお客様に提供します。
- 通話品質のエンドツーエンドを管理します。
- PSTN サービスに対する個別の料金。

Microsoft は、通信事業者を管理していない。 Microsoft は PBX (Microsoft Phone System) と Teams クライアントを提供しています。 また、Microsoft は電話を認定し、Microsoft Phone System で使用できる SPC を認定します。 通信事業者を選択する前に、お客様の選択に認定済みの SBC が付いていて、音声品質をエンドツーエンドで管理できる必要があります。

シナリオを構成するための技術的な実装手順を次に示します。

**通信事業者のみ:**
1. SBC を展開し、認定された SBC ベンダーからの指示に従ってホスティング [シナリオ用に構成します](#deploy-and-configure-the-sbc)。
2. キャリア テナントにベース ドメイン名を登録し、ワイルドカード証明書を要求します。
3. ベース ドメインの一部であるすべての顧客のサブドメインを登録します。

**お客様のグローバル管理者が利用している通信事業者:**
1. サブドメイン名を顧客テナントに追加します。
2. サブドメイン名をアクティブ化します。
3. 通信事業者から顧客テナントにトランクを構成し、ユーザーをプロビジョニングします。

*DNS の基本と、Microsoft 365 または Office 365 でのドメイン名の管理方法を理解してください。さらに [進む前に、Microsoft 365 または Office 365 ドメイン](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) に関するヘルプを参照してください。*

## <a name="deploy-and-configure-the-sbc"></a>SBC を展開して構成する

SBC ホスティング シナリオ用の SBC を展開および構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。

- **AudioCodes:** [ダイレクト](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)ルーティング構成のメモ、"AudioCodes SBC を Microsoft Teams ダイレクト ルーティング ホスティング モデル構成メモに接続する" で説明されている SBC ホスティング シナリオの構成。 
- **Oracle:** [ダイレクト ルーティング構成に関する注意事項](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)、SBC ホスティング シナリオの構成については、「Microsoft」セクションを参照してください。 
- **リボンのコミュニケーション:** リボン コア シリーズの SBC を構成する方法およびこのページのリボンのベスト プラクティス - Microsoft Teams ダイレクト ルーティング [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)用の携帯電話会社の構成については、リボン通信 [SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) Core Microsoft Teams 構成ガイドを参照してください。
- **TE-Systems (anynode):**  複数のテナントに対して anynode SBC を構成する方法のドキュメントと例については [、TE-Systems コミュニティ](https://community.te-systems.de/) ページに登録してください。
- **メタスイッチ:**  複数のテナントで Perimeta SBC を有効にする方法のドキュメントについては [、Metaswitch コミュニティ](https://manuals.metaswitch.com/MAN39555) ページに登録してください。

> [!NOTE]
> "連絡先" ヘッダーの構成方法にご注意ください。 連絡先ヘッダーは、受信した招待メッセージで顧客テナントを検索するために使用されます。 

## <a name="register-a-base-domain-and-subdomains"></a>ベース ドメインとサブドメインを登録する

ホスティングシナリオでは、次を作成する必要があります。
- 通信事業者が所有する 1 つのベース ドメイン名。
- すべての顧客テナントのベース ドメイン名の一部であるサブドメイン。

次の例では、次の手順を実行します。
- Adatum は、インターネットおよびテレフォニー サービスを提供することで、複数の顧客にサービスを提供する通信事業者です。
- Woodgrove Bank、Contoso、Adventure Works は、Microsoft 365 または Office 365 ドメインを持っているが、Adatum からテレフォニー サービスを受け取る 3 人のお客様です。

サブドメインは、Microsoft 365 または Office 365 に招待を送信するときに、顧客用に構成されるトランクの FQDN 名と連絡先ヘッダーの FQDN と一致する必要があります。  

呼び出しが Microsoft 365 または Office 365 ダイレクト ルーティング インターフェイスに到着すると、インターフェイスは連絡先ヘッダーを使用して、ユーザーを検索する必要があるテナントを検索します。 ダイレクト ルーティングでは、複数のテナントで重複する可能性がある DID 以外の番号を持つお客様もいます。 そのため、電話番号でユーザーを検索するテナントを正確に識別するには、連絡先ヘッダーの FQDN 名が必要です。

*Microsoft  [365 または Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織でのドメイン名の作成の詳細については、365 のドメインに関するヘルプOffice参照してください。*

次の図は、ベース ドメイン、サブドメイン、連絡先ヘッダーの要件をまとめた図です。

![ドメインと連絡先ヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

SBC では、接続を認証するために証明書が必要です。 SBC ホスティング のシナリオでは、通信事業者は CN または SAN .base_domain *\* \* (.customers.adatum.biz など)* を含む証明書を要求する必要があります。 この証明書は、1 つの SBC から提供された複数のテナントへの接続を認証するために使用できます。


次の表は、1 つの構成の例です。


|新しいドメイン名 |種類|登録済み  |SBC 用証明書 CN/SAN  |例のテナントの既定のドメイン  |ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに表示する必要があります。|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     通信事業者テナントの場合  |    \*.customers.adatum.biz  |   adatum.biz      |NA、これはサービス テナント、ユーザーなし |
|sbc1.customers.adatum.biz|    サブドメイン  |    顧客テナントの場合  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   サブドメイン | 顧客テナントの場合   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   サブドメイン | 顧客テナントの場合 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

ベースとサブドメインを構成するには、次に説明する手順に従ってください。 この例では、1 人の顧客のベース ドメイン名 (customers.adatum.biz) とサブドメイン (Woodgrove Bank テナントの sbc1.customers.adatum.biz) を構成します。

> [!NOTE]
> このsbcX.customers.adatum.bizを使用して、キャリア テナントで音声を有効にします。 sbcX には、任意の一意の有効な英数字ホスト名を指定できます。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>キャリア テナントでベース ドメイン名を登録する

**これらのアクションは、通信事業者テナントで実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>通信事業者テナントに適切な権限を持っている必要があります

新しいドメインを追加できるのは、グローバル管理者として Microsoft 365 管理センターにサインインしている場合のみです。 

役割を検証するには、Microsoft 365 管理センターにサインインしてください ([アクティブなユーザー] に移動し、グローバル管理者の役割を持っているか https://portal.office.com)   >  確認します)。 

管理者ロールの詳細と、Microsoft 365 または Office 365 でロールを割り当てる方法については、「管理者ロールについて」を [参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>テナントにベース ドメインを追加して確認する

1. Microsoft 365 管理センターで、[ドメインの追加のセットアップ  >  **] に**  >  **移動します**。
2. [所有 **するドメインを入力してください] ボックス** に、ベース ドメインの FQDN を入力します。 次の例では、ベース ドメインは *customers.adatum.biz。*

    ![[ドメインの追加] ページを示すスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. **[次へ]** をクリックします。
4. この例では、テナントは既にadatum.bizドメイン名として使用されています。 既に登録されている名前のサブドメインcustomers.adatum.biz、追加の確認は求めされません。 ただし、以前に確認されていない FQDN を追加する場合は、確認プロセスを実行する必要があります。 確認プロセスについては、以下 [で説明します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![確認済みドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5. [ **次へ]** をクリックし **、[DNS** 設定の更新] ページで **[DNS** レコードを自分で追加する] を選び、[次へ] をクリック **します**。
6. 次のページで、すべての値をクリアし (Exchange、SharePoint、または Teams/Skype for Business のドメイン名を使用しない場合)、[次へ] をクリックし、[完了] をクリックします。 新しいドメインがセットアップ完了状態に設定済みである必要があります。

    ![セットアップが完了した状態のドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>ドメイン名をアクティブ化する

ドメイン名を登録したら、少なくとも 1 人の E1、E3、または E5 ライセンスを取得したユーザーを追加し、作成されたベース ドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当て、ドメイン名をアクティブ化する必要があります。 ライセンスは、ドメインのライセンス認証後に取り消されます (最大 24 時間かかる場合があります)。

> [!NOTE]
> Skype for Business 構成が削除されるのを避けるために、Carrier テナントは、少なくとも 1 つの E1/E3/E5/M365 Business ライセンスをテナントに割り当て続ける必要があります。 

*Microsoft [365 または Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織でのユーザーの追加の詳細については、Microsoft 365 または Office Office 365 ドメインに関するヘルプを参照してください。*

例: test@customers.adatum.biz

![ベース ドメインのライセンス認証ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>顧客テナントでサブドメイン名を登録する

すべての顧客に一意のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名を持つsbc1.customers.adatum.bizにサブドメイン の名前を作成woodgrovebank.us。

**以下のすべてのアクションは、顧客テナントに含されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>顧客テナントに適切な権限を持っている必要があります

新しいドメインを追加できるのは、グローバル管理者として Microsoft 365 管理センターにサインインしている場合のみです。 

役割を検証するには、Microsoft 365 管理センターにサインインしてください ([アクティブなユーザー] に移動し、グローバル管理者の役割を持っているか https://portal.office.com)   >  確認します)。 

管理者ロールの詳細と、Microsoft 365 または Office 365 でロールを割り当てる方法については、「管理者ロールについて」を [参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>サブドメインを顧客テナントに追加して確認する
1. Microsoft 365 管理センターで、[ドメインの追加のセットアップ  >  **] に**  >  **移動します**。
2. [所有 **するドメインを入力してください]** ボックスに、このテナントのサブドメインの FQDN を入力します。 次の例では、サブドメインはsbc1.customers.adatum.biz。

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. **[次へ]** をクリックします。
4. FQDN がテナントに登録されていません。 次の手順では、ドメインを確認する必要があります。 代 **わりに [TXT レコードの追加] を選択します**。 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. [ **次へ]** をクリックし、ドメイン名を確認するために生成された TXT 値をメモします。

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 通信事業者の DNS ホスティング プロバイダーの前の手順の値を使用して TXT レコードを作成します。

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    詳細については、「任意の DNS ホスティング プロバイダー [で DNS レコードを作成する」を参照してください](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 顧客の Microsoft 365 管理センターに戻り、[確認] を **クリックします**。 
8. 次のページで **、[DNS** レコードを自分で追加して、[次へ] をクリック **します**。

    ![[DNS 設定の更新] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. [オンライン **サービスの選択] ページで、** すべてのオプションをオフにし、[次へ] をクリック **します**。

    ![[オンライン サービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. [DNS **設定** の更新 **] ページで [完了] をクリック** します。

    ![[DNS 設定の更新] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. 状態が [セットアップ完了 **] に設定されています**。 
    
    ![セットアップ完了の状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> 直接ルート トランクを追加するには、個々のクライアントのベース URL とサブドメインが同じテナント上に _設定されている必要_ があります。

### <a name="activate-the-subdomain-name"></a>サブドメイン名をアクティブにする

ドメイン名を登録したら、少なくとも 1 人のユーザーを追加して SIP アドレスを割り当て、顧客テナントで作成されたサブドメインと一致する SIP アドレスの FQDN 部分を割り当てる必要があります。 ライセンスは、サブドメインのライセンス認証後にユーザーから取り消されます (最大 24 時間かかる場合があります)。

*Microsoft [365 または Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 組織でのユーザーの追加の詳細については、Microsoft 365 または Office Office 365 ドメインに関するヘルプを参照してください。*

例: test@sbc1.customers.adatum.biz

![サブドメイン ページのアクティブ化のスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクを作成してユーザーをプロビジョニングする

最初のリリースのダイレクト ルーティングでは、Microsoft は New-CSOnlinePSTNGateway を使用して、サービスを受け取った各テナント (顧客テナント) にトランクを追加する必要がありました。

ただし、次の 2 つの理由で、これが最適であることが証明されたわけではありません。
 
- **オーバーヘッド管理**。 たとえば、SBC のオフロードや水切りは、メディア バイパスの有効化や無効化など、一部のパラメーターを変更します。 ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントでパラメーターを変更する必要がありますが、実際には同じ SBC です。 

-  **オーバーヘッド処理**。 トランク正常性データの収集と監視 - 実際には、同じ SBC と同じ物理トランクである複数の論理トランクから収集された SIP オプションは、ルーティング データの処理を遅くします。
 
このフィードバックに基づいて、Microsoft は顧客テナントのトランクをプロビジョニングする新しいロジックを取り入れしています。

2 つの新しいエンティティが導入されました。
-    New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true など、コマンド New-CSOnlinePSTNGateway を使用してキャリア テナントに登録されたキャリア トランク。

-    登録を必要としない派生トランク。 単に、キャリア トランクから追加された目的のホスト名です。 このパラメーターは、すべての構成パラメーターをキャリア トランクから取得します。 派生トランクは PowerShell で作成する必要はなかった。また、キャリア トランクとの関連付けは FQDN 名に基づいて行います (詳細については以下を参照してください)。

**プロビジョニング ロジックと例**

-    通信事業者は、1 つのトランク (キャリア ドメイン内のキャリア トランク) をセットアップして管理する必要がある場合にのみ、Set-CSOnlinePSTNGatewayします。 上の例では、次adatum.biz。
-    顧客テナントでは、通信事業者は派生トランク FQDN をユーザーの音声ルーティング ポリシーに追加する必要があります。 トランクに対してNew-CSOnlinePSTNGatewayする必要はありません。
-    派生トランクは、名前が示す通り、キャリア トランクからすべての構成パラメーターを継承または派生します。 例:
-    Customers.adatum.biz – キャリア テナントで作成する必要があるキャリア トランク。
-    Sbc1.customers.adatum.biz – PowerShell で作成する必要はない、顧客テナントの派生トランクです。  顧客テナントの派生トランクの名前をオンライン音声ルーティング ポリシーに追加するだけで、その名前を作成せずに追加できます。
-   キャリアは、派生トランク FQDN をキャリア SBC IP アドレスに解決する DNS レコードをセットアップする必要があります。

-    キャリア トランク (キャリア テナント上) に加えた変更は、派生トランクに自動的に適用されます。 たとえば、キャリアはキャリア トランク上の SIP ポートを変更できます。この変更は、すべての派生トランクに適用されます。 トランクを構成する新しいロジックにより、すべてのテナントに移動してすべてのトランクのパラメーターを変更する必要がなさ、管理が簡素化されます。
-    オプションは、キャリア トランク FQDN にのみ送信されます。 キャリア トランクの正常性状態は、すべての派生トランクに適用され、ルーティングの決定に使用されます。 ダイレクト ルーティング オプションの [詳細については、以下を参照してください](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。
-    キャリアはキャリアのトランクを流し込み、すべての派生トランクも同様に流し込む可能性があります。 
 

**前のモデルからキャリア トランクへの移行**
 
通信事業者がホストするモデルの現在の実装から新しいモデルに移行するには、通信事業者が顧客テナントのトランクを再構成する必要があります。 顧客テナントからトランクを削除するには、Remove-CSOnlinePSTNGatewayを使用します (通信事業者のテナントにトランクを残します)。

通信事業者と派生トランク モデルを使用した監視とプロビジョニングを強化する予定で、できるだけ早く新しいソリューションに移行することを強くお勧めします。
 

連絡先ヘッダーでサブドメインの FQDN 名を送信する構成については [、SBC](#deploy-and-configure-the-sbc) ベンダーの手順を参照してください。

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Muti テナントのフェールオーバーをセットアップする場合の考慮事項 

マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。

- テナントごとに、2 つの異なる SPC の FQDN を追加します。  次に例を示します。

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- ユーザーのオンライン音声ルーティング ポリシーで、両方の SPC を指定します。  1 つの SBC が失敗した場合、ルーティング ポリシーは 2 つ目の SBC に通話をルーティングします。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
