---
title: セッション ボーダー コントローラーの構成 - 複数のテナント
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 1 つのセッション ボーダー コントローラー (SBC) を構成して、Microsoft パートナーや PSTN 通信事業者の複数のテナントにサービスを提供する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 570709730f7563b30b98626395f6b0a72fc1ac48
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392297"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントにセッション ボーダー コントローラーを構成する

ダイレクト ルーティングでは、複数のテナントにサービスを提供する 1 つのセッション ボーダー コントローラー (SBC) の構成がサポートされています。

> [!NOTE]
> このシナリオは、このドキュメントの後半で「通信事業者」と呼ばれるMicrosoftパートナーや PSTN 通信事業者向けに設計されています。 通信事業者は、Microsoft Teams に配信されるテレフォニー サービスを顧客に販売します。 

通信事業者:
- データセンターで SBC を展開および管理します (お客様は SBC を実装する必要がなく、Teams クライアントの通信事業者からテレフォニー サービスを受け取ります)。
- SBC を複数のテナントに相互接続します。
- 公衆交換電話網 (PSTN) サービスを顧客に提供します。
- 通話品質をエンドツーエンドで管理します。
- PSTN サービスの場合は別途料金が発生します。

Microsoftは通信事業者を管理しません。 Microsoftでは、電話システム (プライベート ブランチ Exchange (PBX) と Teams クライアント) が提供されます。 また、Microsoftは電話を認定し、電話システムで使用できる SBC を認定します。 通信事業者を選択する前に、選択に認定された SBC があり、音声品質をエンドツーエンドで管理できることを確認します。

シナリオを構成するための技術的な実装手順を次に示します。

**運送業者のみ:**
1. SBC をデプロイし、 [認定された SBC ベンダーの指示](#deploy-and-configure-the-sbc)に従って、ホスティング シナリオ用に構成します。
2. キャリア テナントに基本ドメイン名を登録し、ワイルドカード証明書を要求します。
3. ベース ドメインの一部であるすべての顧客のサブドメインを登録します。

**顧客全体管理者を持つ運送業者:**
1. サブドメイン名を顧客テナントに追加します。
2. サブドメイン名をアクティブにします。
3. 通信事業者から顧客テナントへのトランクを構成し、ユーザーをプロビジョニングします。

*DNS の基本とドメイン名の管理方法については、Microsoft 365 を参照してください。さらに進 [む前に、「Microsoft 365 ドメインに関するヘルプを表示する](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。*

## <a name="deploy-and-configure-the-sbc"></a>SBC のデプロイと構成

SBC ホスティング シナリオ用に SBC を展開および構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。

- **AudioCodes:**「AudioCodes SBC を Teams ダイレクト ルーティング ホスティング モデルの構成ノートにMicrosoftに接続する」で説明されている SBC ホスティング シナリオの構成については、「ダイレクト ルーティング [構成に](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)関するメモ」を参照してください。 
- **Oracle：**「Microsoft」セクションで説明されている SBC ホスティング シナリオの構成については、「[ダイレクト ルーティング構成に](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)関する注意事項」を参照してください。 
- **リボンコミュニケーション:** リボン コア シリーズの SBC を構成する方法のドキュメントについては、「[リボン コミュニケーション SBC Core Microsoft Teams 構成ガイド](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide)」を参照してください。 [「リボンのベスト プラクティス - Microsoft Teams ダイレクト ルーティング SBC Edge 用の通信事業者の構成](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)」も参照してください。
- **TE-Systems (anynode):** 複数のテナントに anynode SBC を構成する方法のドキュメントと例については、 [TE-Systems コミュニティ ページ](https://community.te-systems.de/) サイトに登録します。
- **メタスイッチ:** 複数のテナントに対して Perimeta SBC を有効にする方法に関するドキュメントについては、 [Metaswitch Community ページ](https://manuals.metaswitch.com/MAN39555) サイトに登録します。

> [!NOTE]
> "連絡先" ヘッダーを構成する方法がわかっていることを確認してください。 連絡先ヘッダーは、受信招待メッセージで顧客テナントを検索するために使用されます。 

## <a name="register-a-base-domain-and-subdomains"></a>基本ドメインとサブドメインを登録する

ホスティング シナリオでは、次を作成する必要があります。

- 通信事業者が所有する 1 つの基本ドメイン名。
- すべての顧客テナントの基本ドメイン名の一部であるサブドメイン。

次の例では、

- Adatum は、インターネットとテレフォニー サービスを提供することで複数の顧客にサービスを提供する通信事業者です。
- Woodgrove Bank、Contoso、Adventure Works は、Microsoft 365 ドメインを持つが、Adatum からテレフォニー サービスを受け取る 3 つの顧客です。

サブドメインは、顧客用に構成されるトランクの FQDN 名と、Invite to Microsoft 365 を送信するときに Contact ヘッダーの FQDN と一致する **必要があります**。 

呼び出しが Microsoft 365 ダイレクト ルーティング インターフェイスに到着すると、インターフェイスは Contact ヘッダーを使用して、ユーザーを検索するテナントを検索します。 ダイレクト ルーティングでは、複数のテナントで重複する可能性がある DID 以外の番号を持つ顧客がいる場合があるため、招待時に電話番号検索は使用されません。 そのため、連絡先ヘッダーの FQDN 名は、電話番号でユーザーを検索する正確なテナントを識別するために必要です。

*Microsoft 365 組織でのドメイン名の作成の詳細については、「[Microsoft 365 ドメインのヘルプを表示する](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。*

次の図は、ベース ドメイン、サブドメイン、Contact ヘッダーの要件をまとめたものです。

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="ドメインと連絡先ヘッダーの要件を示す図。" lightbox="media/direct-routing-1-sbc-requirements.png":::

SBC では、接続を認証するための証明書が必要です。 SBC ホスティング シナリオでは、通信事業者は CN または SAN *\*.base_domain (.customers.adatum.biz など \*) を* 使用して証明書を要求する必要があります。 この証明書は、1 つの SBC から提供される複数のテナントへの接続を認証するために使用できます。

次の表は、1 つの構成の例です。


|新しいドメイン名 |種類|登録  |SBC の証明書 CN/SAN  |この例のテナントの既定のドメイン  |ユーザーへの呼び出しを送信するときに、連絡先ヘッダーに SBC が存在する必要がある FQDN 名|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    ベース     |     通信事業者のテナント  |    \*.customers.adatum.biz  |   adatum.biz      |NA、これはサービス テナントであり、ユーザーなし |
|sbc1.customers.adatum.biz|    サブドメイン  |    顧客テナント内  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   サブドメイン | 顧客テナント内   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   サブドメイン | 顧客テナント内 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

ベースとサブドメインを構成するには、以下で説明する手順に従います。 次の使用例は、ベース ドメイン名 (customers.adatum.biz) と 1 人の顧客 (Woodgrove Bank テナントの sbc1.customers.adatum.biz) のサブドメインを構成します。

> [!NOTE]
> sbcX.customers.adatum.biz を使用して、通信事業者テナントで音声を有効にします。sbcX には、任意の一意で有効な英数字ホスト名を指定できます。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>キャリア テナントに基本ドメイン名を登録する

**これらのアクションは、通信事業者テナントで実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>運送業者テナントに適切な権限があることを確認する

グローバル管理者としてMicrosoft 365 管理センターにサインインした場合にのみ、新しいドメインを追加できます。 

持っているロールを検証するには、Microsoft 365 管理センターにサインインします (https://portal.office.com)[**ユーザー** > **] [アクティブ なユーザー**] に移動し、グローバル管理者ロールがあることを確認します。 

管理者ロールと、Microsoft 365 でロールを割り当てる方法の詳細については、「[管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)」を参照してください。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>テナントにベース ドメインを追加して確認する

1. Microsoft 365 管理センターで、[**ドメインのセットアップ** > ] [**ドメインの** > **追加]** の順に移動します。

2. [ **自分が所有するドメインを入力** する] ボックスに、基本ドメインの FQDN を入力します。 次の例では、基本ドメインが *customers.adatum.biz* されています。

3. **[次へ]** をクリックします。

4. この例では、テナントは既に検証済みドメイン名として adatum.biz しています。 customers.adatum.biz は既に登録されている名前のサブドメインであるため、ウィザードは追加の検証を求めません。 ただし、以前に検証されていない FQDN を追加する場合は、検証のプロセスを実行する必要があります。 検証のプロセス [を以下に示します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

5. [ **次へ**] を選択し **、[DNS 設定の更新]** ページで [ **自分で DNS レコードを追加します** ] を選択し、[ **次へ**] を選択します。

6. 次のページで、すべての値をクリアします (Exchange、SharePoint、Teams、またはSkype for Businessのドメイン名を使用する場合を除く)、[**次へ**] を選択し、[完了] を選択 **します**。 新しいドメインが [セットアップの完了] 状態になっていることを確認します。

### <a name="activate-the-domain-name"></a>ドメイン名をアクティブ化する

ドメイン名を登録したら、少なくとも 1 つの Teams ライセンスユーザーまたはリソース アカウントを追加して、ドメイン名をアクティブ化する必要があります。 受け入れ可能なアカウントには、次のいずれかの SKU でライセンスが付与されます。

- Office 365 E1/E3/E5 または Microsoft 365 E3/E5 を持つユーザー アカウント。
- Office 365 A1/A3/A5 または Microsoft 365 A1/A3/A5 を持つユーザー アカウント。
- Office 365 F3 または Microsoft 365 F1/F3 を持つユーザー アカウント。
- Office 365 G1/G3/G5 または Microsoft 365 G3/G5 を持つユーザー アカウント。
- Microsoft 365 Business Basic/Standard/Premium のユーザー アカウント。
- **Microsoft Teams 共有デバイス** ライセンスを持つユーザー アカウント。
- **Microsoft Teams 電話 リソース アカウント** ライセンスを持つリソース アカウント。

さらに、アカウントの UPN (ユーザー プリンシパル名) またはオンプレミスの SIP アドレスSkype for Businessは、新しく作成されたドメインと同じ FQDN を使用する必要があります。

Microsoft 365 組織でのユーザーの追加の詳細については、「[Microsoft 365 ドメインに関するヘルプを表示する](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。

例: test@customers.adatum.biz

![基本ドメインのアクティブ化ページのスクリーンショット。](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>顧客テナントにサブドメイン名を登録する

顧客ごとに一意のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名 woodgrovebank.us を持つテナントにサブドメイン sbc1.customers.adatum.biz を作成します。

**以下のすべてのアクションは、顧客テナントにあります。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>顧客テナントに適切な権限があることを確認する

グローバル管理者としてMicrosoft 365 管理センターにサインインした場合にのみ、新しいドメインを追加できます。 

持っているロールを検証するには、Microsoft 365 管理センターにサインインします (https://portal.office.com)[**ユーザー** > **] [アクティブ なユーザー**] に移動し、グローバル管理者ロールがあることを確認します。 

管理者ロールと、Microsoft 365 でロールを割り当てる方法の詳細については、「[管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)」を参照してください。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>顧客テナントにサブドメインを追加して確認する

1. Microsoft 365 管理センターで、[**ドメインのセットアップ** > ] [**ドメインの** > **追加]** の順に移動します。

2. [ **自分が所有するドメインを入力** する] ボックスに、このテナントのサブドメインの FQDN を入力します。 次の例では、サブドメインが sbc1.customers.adatum.biz されています。

3. [**次へ**] を選択します。

4. FQDN はテナントに登録されていません。 次の手順では、ドメインを確認する必要があります。 **代わりに [TXT レコードの追加]** を選択します。 

5. [ **次へ**] を選択し、生成された TXT 値を書き留め、ドメイン名を確認します。

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット。](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 通信事業者の DNS ホスティング プロバイダーの前の手順の値を使用して TXT レコードを作成します。

    詳細については、「任意の [DNS ホスティング プロバイダーで DNS レコードを作成する](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)」を参照してください。

7. 顧客のMicrosoft 365 管理センターに移動し、[確認] を選択 **します**。 

8. 次のページで、[ **自分で DNS レコードを追加します]** を選択し、[ **次へ**] を選択します。

9. [**オンライン サービスの選択]** ページで、すべてのオプションをオフにして、[**次へ**] を選択します。

10. [**DNS 設定の更新**] ページで **[完了] を選択します**。

11. 状態が **[セットアップ完了]** になっていることを確認します。

    ![セットアップ完了の状態を示すページのスクリーンショット。](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> _直接ルート_ トランクを追加できるようにするには、個々のクライアントのベース URL とサブドメインが同じテナント上にある必要があります。

### <a name="activate-the-subdomain-name"></a>サブドメイン名をアクティブにする

サブドメイン名を登録したら、少なくとも 1 つの Teams ライセンスユーザーまたはリソース アカウントを追加してアクティブ化する必要があります。 受け入れ可能なアカウントには、次のいずれかの SKU でライセンスが付与されます。

-   Office 365 E1/E3/E5/A3/A5 または Microsoft 365 E3/E5/A3/A5 のユーザー アカウント
-   Office 365 F1/F3 または Microsoft 365 F1/F3 のユーザー アカウント
-   Microsoft 365 Business Basic/Standard/Premium プランと G3/G5 プランを持つユーザー アカウント
-   **Microsoft Teams 共有デバイス** ライセンスを持つユーザー アカウント
-   **Microsoft Teams 電話 リソース アカウント** ライセンスを持つリソース アカウント

さらに、アカウントの UPN (ユーザー プリンシパル名) またはオンプレミスの SIP アドレスSkype for Businessは、新しく作成されたサブドメインと同じ FQDN を使用する必要があります。

Microsoft 365 組織でのユーザーの追加の詳細については、「[Microsoft 365 のヘルプを表示](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)する」を参照してください。

例: test@sbc1.customers.adatum.biz

![サブドメイン ページのアクティブ化のスクリーンショット。](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクを作成し、ユーザーをプロビジョニングする

ダイレクト ルーティングの最初のリリースでは、MicrosoftNew-CSOnlinePSTNGateway コマンドレットを使用して、サービスを提供される各テナント (顧客テナント) にトランクを追加する必要があります。

ただし、次の 2 つの理由から、この方法が最適であることが証明されていません。
 
- **オーバーヘッド管理**。 たとえば、SBC をオフロードまたはドレインすると、メディア バイパスの有効化や無効化など、いくつかのパラメーターが変更されます。 ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実際には同じ SBC です。 

-  **オーバーヘッド処理**。 トランク正常性データの収集と監視 - 実際には、同じ SBC と同じ物理トランクである複数の論理トランクから収集された SIP オプションによって、ルーティング データの処理が遅くなります。
 
このフィードバックに基づいて、Microsoftは、顧客テナントのトランクをプロビジョニングするための新しいロジックを導入しています。

2 つの新しいエンティティが導入されました。

- コマンド New-CSOnlinePSTNGateway を使用して、キャリア テナントに登録されたキャリア トランク。 次に例を示します。 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- 登録を必要としない派生トランク。 これは、単にキャリア トランクから追加された目的のホスト名です。 すべての構成パラメーターがキャリア トランクから派生します。 キャリア トランクとの関連付けは、FQDN 名に基づいています (以下の詳細を参照)。

**プロビジョニング ロジックと例**

- 通信事業者は、Set-CSOnlinePSTNGateway コマンドを使用して、1 つのトランク (キャリア ドメイン内のキャリア トランク) のみを設定して管理する必要があります。 上記の例では、adatum.biz されています。

- 顧客テナントでは、通信事業者は音声ルートに派生トランク FQDN を追加する必要があります。 トランクのNew-CSOnlinePSTNGatewayを実行する必要はありません。

- 派生トランクは、名前が示すように、キャリア トランクからすべての構成パラメーターを継承または派生します。 

例：
- Customers.adatum.biz – キャリア テナントで作成する必要があるキャリア トランク。

- Sbc1.customers.adatum.biz – 顧客テナントの派生トランク。 顧客テナントの派生トランクの名前は、作成せずに音声ルートに追加できます。

- 通信事業者は、派生トランク FQDN をキャリア SBC IP アドレスに解決する DNS レコードを設定する必要があります。

- (キャリア テナント上の) キャリア トランクに加えられた変更は、派生トランクに自動的に適用されます。 たとえば、通信事業者はキャリア トランク上の SIP ポートを変更でき、この変更はすべての派生トランクに適用されます。 トランクを構成するための新しいロジックにより、すべてのテナントに移動し、すべてのトランクでパラメーターを変更する必要がないので、管理が簡素化されます。

- オプションは、キャリア トランク FQDN にのみ送信されます。 キャリア トランクの正常性状態は、すべての派生トランクに適用され、ルーティングの決定に使用されます。 [ダイレクト ルーティング オプション](./direct-routing-monitor-and-troubleshoot.md)の詳細については、以下を参照してください。

- キャリアはキャリア トランクをドレインでき、すべての派生トランクもドレインされます。 
 
> [!NOTE]
> キャリア トランクに適用される番号変換ルールは、派生トランクには適用されません。 これは既知の問題です。 別のソリューションとして、顧客のテナントごとに番号変換ルールを作成する必要があります。

**前のモデルからキャリア トランクへの移行**
 
キャリアホストモデルの現在の実装から新しいモデルへの移行では、通信事業者は顧客テナントのトランクを再構成する必要があります。 Remove-CSOnlinePSTNGatewayを使用して顧客テナントからトランクを削除します (トランクはキャリア テナントに残します)。

通信事業者と派生トランク モデルを使用した監視とプロビジョニングを強化するため、できるだけ早く新しいソリューションに移行することを強くお勧めします。
 
Contact ヘッダーでサブドメインの FQDN 名を送信する構成の詳細については、 [SBC ベンダーの手順](#deploy-and-configure-the-sbc)を参照してください。

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>マルチテナント フェールオーバーの設定に関する考慮事項 

マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。

- テナントごとに、2 つの異なる SBC の FQDN を追加します。 次に例を示します。

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- [オンライン音声ルート] で、両方の SBC を指定します。 1 つの SBC が失敗した場合、ルーティング ポリシーは 2 番目の SBC に呼び出しをルーティングします。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
