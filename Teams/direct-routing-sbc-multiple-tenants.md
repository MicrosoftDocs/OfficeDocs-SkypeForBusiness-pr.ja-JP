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
description: Microsoft パートナーまたは PSTN 通信事業者の複数のテナントにサービスを提供するように 1 つのセッション ボーダー コントローラー (SBC) を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be75743752f34024baf7b2fd017557c2f0044ba6
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823688"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントにセッション ボーダー コントローラーを構成する

ダイレクト ルーティングでは、複数のテナントにサービスを提供するように 1 つのセッション ボーダー コントローラー (SBC) を構成できます。

> [!NOTE]
> このシナリオは、このドキュメントの後半で説明する Microsoft パートナーまたは PSTN 通信事業者向けに設計されています。 通信事業者は、顧客にMicrosoft Teamsに配信されるテレフォニー サービスを販売しています。 

運送業者:
- データセンターに SBC をデプロイおよび管理します (お客様は SBC を実装する必要がなく、Teams クライアントの通信事業者からテレフォニー サービスを受け取ります)。
- SBC を複数のテナントに相互接続します。
- 公衆交換電話網 (PSTN) サービスを顧客に提供します。
- 通話品質をエンドツーエンドで管理します。
- PSTN サービスに対して個別に課金されます。

Microsoft は運送業者を管理していません。 Microsoft では、電話システム (プライベート ブランチ Exchange (PBX) とTeams クライアントを提供しています。 Microsoft はまた、電話を認証し、電話システムで使用できる SBC を認定します。 キャリアを選択する前に、選択した SBC が認定されており、音声品質をエンドツーエンドで管理できることを確認します。

シナリオを構成するための技術的な実装手順を次に示します。

**運送業者のみ:**
1. SBC をデプロイし、 [認定された SBC ベンダーの指示](#deploy-and-configure-the-sbc)に従ってホスティング シナリオ用に構成します。
2. キャリア テナントに基本ドメイン名を登録し、ワイルドカード証明書を要求します。
3. 基本ドメインの一部である顧客ごとにサブドメインを登録します。

**お客様のグローバル管理者を含む運送業者:**
1. サブドメイン名を顧客テナントに追加します。
2. サブドメイン名をアクティブにします。
3. キャリアから顧客テナントへのトランクを構成し、ユーザーをプロビジョニングします。

*DNS の基本と、Microsoft 365でドメイン名を管理する方法について理解していることを確認します。さらに進 [む前に、Microsoft 365 ドメインに関するヘルプを](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)参照してください。*

## <a name="deploy-and-configure-the-sbc"></a>SBC をデプロイして構成する

SBC ホスティング シナリオ用に SBC をデプロイおよび構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。

- **AudioCodes:**「AudioCodes SBC を [Microsoft Teams ダイレクト ルーティング](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) ホスティング モデル構成ノートに接続する」で説明されているように、SBC ホスティング シナリオの構成に関するダイレクト ルーティング構成に関する注意事項を参照してください。 
- **Oracle：** 「Microsoft」セクションで説明されているように、SBC ホスティング シナリオの構成については、 [ダイレクト ルーティング構成に](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) 関する注意事項を参照してください。 
- **リボン通信:** Ribbon Core Series SBC を構成する方法については、「[Ribbon Communications SBC Core Microsoft Teams 構成ガイド](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)」を参照してください。 [「リボンのベスト プラクティス - Microsoft Teams ダイレクト ルーティング SBC Edge 用の通信事業者の構成](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)」も参照してください。
- **TE-Systems (anynode):** 複数のテナントに anynode SBC を構成する方法のドキュメントと例については、[TE-Systems Community ページ](https://community.te-systems.de/) サイトに登録します。
- **Metaswitch:** 複数のテナントに対して Perimeta SBC を有効にする方法に関するドキュメントについては、[Metaswitch Community ページ](https://manuals.metaswitch.com/MAN39555) サイトに登録します。

> [!NOTE]
> "Contact" ヘッダーを構成する方法を理解していることを確認します。 連絡先ヘッダーは、受信招待メッセージで顧客テナントを検索するために使用されます。 

## <a name="register-a-base-domain-and-subdomains"></a>基本ドメインとサブドメインを登録する

ホスティング シナリオでは、次を作成する必要があります。

- 通信事業者が所有する 1 つの基本ドメイン名。
- すべての顧客テナントのベース ドメイン名の一部であるサブドメイン。

次の例では、

- Adatum は、インターネットおよびテレフォニー サービスを提供することで、複数の顧客にサービスを提供する通信事業者です。
- Woodgrove Bank、Contoso、Adventure Works は、Microsoft 365 ドメインを持ち、Adatum からテレフォニー サービスを受け取る 3 人の顧客です。

サブドメインは、顧客に対して構成されるトランクの FQDN 名と、招待をMicrosoft 365に送信するときに連絡先ヘッダーの FQDN と一致する **必要があります**。 

呼び出しがMicrosoft 365ダイレクト ルーティング インターフェイスに到着すると、インターフェイスは Contact ヘッダーを使用して、ユーザーを検索する必要があるテナントを見つけます。 一部の顧客は、複数のテナントで重複する可能性がある DID 以外の番号を持つ可能性があるため、ダイレクト ルーティングでは招待で電話番号参照を使用しません。 そのため、電話番号でユーザーを検索する正確なテナントを識別するには、連絡先ヘッダーの FQDN 名が必要です。

*Microsoft 365組織でのドメイン名の作成の詳細については、「[Microsoft 365 ドメインのヘルプを参照](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)してください。*

次の図は、基本ドメイン、サブドメイン、連絡先ヘッダーに対する要件をまとめたものです。

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="ドメインと連絡先ヘッダーの要件を示す図。" lightbox="media/direct-routing-1-sbc-requirements.png":::

SBC には、接続を認証するための証明書が必要です。 SBC ホスティング シナリオの場合、通信事業者は CN または SAN *\*.base_domain (.customers.adatum.biz など \*)* を使用して証明書を要求する必要があります。 この証明書は、1 つの SBC から提供される複数のテナントへの接続を認証するために使用できます。

次の表は、1 つの構成の例です。


|新しいドメイン名 |種類|登録  |SBC の証明書 CN/SAN  |例のテナントの既定のドメイン  |ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに表示する必要がある FQDN 名|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    ベース     |     キャリア テナント内  |    \*.customers.adatum.biz  |   adatum.biz      |NA、これはサービス テナントであり、ユーザーはいません |
|sbc1.customers.adatum.biz|    サブドメイン  |    顧客テナント内  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   サブドメイン | 顧客テナント内   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   サブドメイン | 顧客テナント内 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

ベースとサブドメインを構成するには、次に説明する手順に従います。 この例では、1 人の顧客 (Woodgrove Bank テナントの sbc1.customers.adatum.biz) の基本ドメイン名 (customers.adatum.biz) とサブドメインを構成します。

> [!NOTE]
> sbcX.customers.adatum.biz を使用して、キャリア テナントで音声を有効にします。sbcX には、任意の一意の有効な英数字ホスト名を指定できます。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>キャリア テナントにベース ドメイン名を登録する

**これらのアクションは、キャリア テナントで実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>キャリア テナントに適切な権限があることを確認する

グローバル管理者としてMicrosoft 365 管理センターにサインインした場合にのみ、新しいドメインを追加できます。 

自分のロールを検証するには、Microsoft 365 管理センターにサインインします (https://portal.office.com)[**ユーザー****アクティブ ユーザー]** >  に移動し、グローバル管理者ロールがあることを確認します。 

管理者ロールと、Microsoft 365でロールを割り当てる方法の詳細については、「[管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)」を参照してください。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>テナントにベース ドメインを追加し、それを確認する

1. Microsoft 365 管理センターで、[**ドメインの追加ドメインの** > **セットアップ]** >  に移動 **します**。

2. [ **所有するドメインを入力** する] ボックスに、ベース ドメインの FQDN を入力します。 次の例では、基本ドメインが *customers.adatum.biz* されています。

3. **[次へ]** をクリックします。

4. この例では、テナントに検証済みのドメイン名として adatum.biz が既に存在します。 customers.adatum.biz は既に登録されている名前のサブドメインであるため、ウィザードは追加の検証を要求しません。 ただし、以前に検証されていない FQDN を追加する場合は、検証のプロセスを実行する必要があります。 検証のプロセスについては、 [以下で説明します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

5. **[次へ**] を選択し、[**DNS 設定の更新**] ページ **で[自分で DNS レコードを追加します**]、[**次へ**] の順に選択します。

6. 次のページで、すべての値をクリアします (Exchange、SharePoint、Teams、またはSkype for Businessにドメイン名を使用する場合を除く)、[**次へ**] を選択し、[完了] を選択 **します**。 新しいドメインが [セットアップの完了] 状態になっていることを確認します。

### <a name="activate-the-domain-name"></a>ドメイン名をアクティブ化する

ドメイン名を登録したら、電話システム ライセンスを持つ少なくとも 1 人のユーザーを追加し、作成されたベース ドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てることで、ドメイン名をアクティブ化する必要があります。

> [!NOTE]
> キャリア テナントは、Skype for Business構成の削除を回避するために、少なくとも 1 つの電話システム ライセンスをテナントに割り当てる必要があります。 

*Microsoft 365組織にユーザーを追加する方法の詳細については、「[Microsoft 365 ドメインに関するヘルプを参照](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)してください。*

たとえば、test@customers.adatum.biz

![ベース ドメインのアクティブ化ページのスクリーンショット。](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>顧客テナントにサブドメイン名を登録する

すべての顧客に一意のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名 woodgrovebank.us を持つサブドメイン sbc1.customers.adatum.biz をテナントに作成します。

**以下のすべてのアクションは、顧客テナントにあります。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>顧客テナントに適切な権限があることを確認する

グローバル管理者としてMicrosoft 365 管理センターにサインインした場合にのみ、新しいドメインを追加できます。 

自分のロールを検証するには、Microsoft 365 管理センターにサインインします (https://portal.office.com)[**ユーザー****アクティブ ユーザー]** >  に移動し、グローバル管理者ロールがあることを確認します。 

管理者ロールと、Microsoft 365でロールを割り当てる方法の詳細については、「[管理者ロールについて](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)」を参照してください。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>顧客テナントにサブドメインを追加して確認する

1. Microsoft 365 管理センターで、[**ドメインの追加ドメインの** > **セットアップ]** >  に移動 **します**。

2. [ **所有するドメインを入力** する] ボックスに、このテナントのサブドメインの FQDN を入力します。 次の例では、サブドメインが sbc1.customers.adatum.biz されています。

3. [**次へ**] を選択します。

4. FQDN はテナントに登録されていません。 次の手順では、ドメインを確認する必要があります。 **代わりに [TXT レコードの追加]** を選択します。 

5. **[次へ**] を選択し、生成された TXT 値をメモしてドメイン名を確認します。

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット。](media/direct-routing-7-sbc-verify-domain-txt.png)

6. キャリアの DNS ホスティング プロバイダーの前の手順の値を使用して TXT レコードを作成します。

    詳細については、「任意の [DNS ホスティング プロバイダーで DNS レコードを作成する](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)」を参照してください。

7. 顧客のMicrosoft 365 管理センターに移動し、[**確認**] を選択します。 

8. 次のページで、[ **自分で DNS レコードを追加します** ] を選択し、[ **次へ**] を選択します。

9. [**オンライン サービスの選択]** ページで、すべてのオプションをクリアし、[**次へ**] を選択します。

10. [**DNS 設定の更新**] ページで **[完了] を選択します**。

11. 状態が **セットアップ完了** であることを確認します。 
    
    ![セットアップ完了の状態を示すページのスクリーンショット。](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> _ダイレクト ルート_ トランクを追加するには、個々のクライアントのベース URL とサブドメインが同じテナント上にある必要があります。

### <a name="activate-the-subdomain-name"></a>サブドメイン名をアクティブ化する

ドメイン名を登録した後、少なくとも 1 人のユーザーを追加してアクティブ化し、顧客テナントで作成されたサブドメインと一致する SIP アドレスの FQDN 部分を持つ SIP アドレスを割り当てる必要があります。 

*Microsoft 365組織にユーザーを追加する方法の詳細については、「[Microsoft 365に関するヘルプを参照](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)してください。*

たとえば、test@sbc1.customers.adatum.biz

![サブドメイン ページのアクティブ化のスクリーンショット。](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクを作成し、ユーザーをプロビジョニングする

Direct Routing の最初のリリースでは、microsoft は、New-CSOnlinePSTNGateway コマンドレットを使用して、各サービステナント (顧客テナント) にトランクを追加する必要があります。

ただし、このメソッドは、次の 2 つの理由で最適であることが証明されていません。
 
- **オーバーヘッド管理**。 たとえば、SBC をオフロードまたはドレインすると、メディア バイパスの有効化や無効化などの一部のパラメーターが変更されます。 ポートを変更するには、(Set-CSOnlinePSTNGateway を実行して) 複数のテナントでパラメーターを変更する必要がありますが、実際には同じ SBC です。 

-  **オーバーヘッド処理**。 トランクの正常性データの収集と監視 - 実際には、同じ SBC と同じ物理トランクである複数の論理トランクから収集された SIP オプションにより、ルーティング データの処理が遅くなります。
 
このフィードバックに基づいて、Microsoft は顧客テナントのトランクをプロビジョニングする新しいロジックを導入しています。

2 つの新しいエンティティが導入されました。

- New-CSOnlinePSTNGateway コマンドを使用して、キャリア テナントに登録されたキャリア トランク。 次に例を示します。 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- 登録を必要としない派生トランク。 これは、単に、キャリア トランクから追加された必要なホスト名です。 すべての構成パラメーターがキャリア トランクから派生します。 派生トランクは PowerShell で作成する必要はありません。また、キャリア トランクとの関連付けは FQDN 名に基づいています (以下の詳細を参照)。

**プロビジョニング ロジックと例**

- 通信事業者は、Set-CSOnlinePSTNGateway コマンドを使用して、1 つのトランク (キャリア ドメイン内のキャリア トランク) のみを設定して管理する必要があります。 上の例では、adatum.biz です。

- カスタマー テナントでは、キャリアは派生トランク FQDN を音声ルートに追加する必要があります。 トランクのNew-CSOnlinePSTNGatewayを実行する必要はありません。

- 派生トランクは、名前が示すように、すべての構成パラメーターをキャリア トランクから継承または派生させます。 

例：
- Customers.adatum.biz – キャリア テナントで作成する必要があるキャリア トランク。

- Sbc1.customers.adatum.biz – PowerShell で作成する必要のない顧客テナント内の派生トランク。 顧客テナントの派生トランクの名前は、作成せずにオンライン音声ルーティング ポリシーに追加できます (登録されている Teams-Voice-Direct Routing-Voice Routes フィールドの SBC の下で、TAC で音声ルーティング ポリシーを設定する場合は派生トランク FQDN を使用します)。

- キャリアは、派生トランク FQDN をキャリア SBC IP アドレスに解決する DNS レコードを設定する必要があります。

- (キャリア テナント上の) キャリア トランクで行われた変更は、派生トランクに自動的に適用されます。 たとえば、通信事業者は、キャリア トランクの SIP ポートを変更でき、この変更はすべての派生トランクに適用されます。 トランクを構成するための新しいロジックにより、すべてのテナントに移動し、すべてのトランクのパラメーターを変更する必要がないため、管理が簡略化されます。

- このオプションは、キャリア トランク FQDN にのみ送信されます。 キャリア トランクの正常性状態は、すべての派生トランクに適用され、ルーティングの決定に使用されます。 [ダイレクト ルーティング オプション](./direct-routing-monitor-and-troubleshoot.md)の詳細については、こちらをご覧ください。

- キャリアはキャリア トランクをドレインでき、派生したすべてのトランクもドレインされます。 
 
> [!NOTE]
> キャリア トランクに適用される番号変換ルールは、派生トランクには適用されません。 これは既知の問題です。 代替ソリューションとして、顧客のテナントごとに番号変換ルールを作成する必要があります。

**前のモデルからキャリア トランクへの移行**
 
キャリア ホステッド モデルの現在の実装から新しいモデルへの移行では、通信事業者は顧客テナントのトランクを再構成する必要があります。 Remove-CSOnlinePSTNGatewayを使用して顧客テナントからトランクを削除する (トランクをキャリア テナントに残す)-

通信事業者と派生トランク モデルを使用して監視とプロビジョニングを強化するため、できるだけ早く新しいソリューションに移行することを非常に推奨します。
 
連絡先ヘッダーでサブドメインの FQDN 名を送信する構成の詳細については、 [SBC ベンダーの手順](#deploy-and-configure-the-sbc)を参照してください。

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>マルチテナント フェールオーバーの設定に関する考慮事項 

マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。

- テナントごとに、2 つの異なる SBC の FQDN を追加します。 次に例を示します。

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- オンライン音声ルートで、両方の SBC を指定します。 1 つの SBC が失敗した場合、ルーティング ポリシーは 2 番目の SBC に呼び出しをルーティングします。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)
