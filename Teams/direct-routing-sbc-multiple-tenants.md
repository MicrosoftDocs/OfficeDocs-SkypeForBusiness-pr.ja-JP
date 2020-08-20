---
title: Session Border Controller を構成する - 複数のテナント
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
description: Microsoft パートナーまたは PSTN のキャリアで複数のテナントを提供するために 1 つのセッション ボーダー コントローラー (SBC) を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91ca12f3e0d9720800ad9b0bcf946df8d31b3e86
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814243"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントにセッション ボーダー コントローラーを構成する

ルーティングでは、1 つのセッション ボーダー コントローラー (SBC) を構成して複数のテナントを満たすようにすることができます。

> [!NOTE]
> このシナリオは、このドキュメントの後半で表される Microsoft パートナーまたは PSTN のキャリアを対象としています。 カナライは、Microsoft Teams に配信されたテレフリー サービスをユーザーに利用します。 

Carrier:
- データセンターで SBC を展開して管理します (SBC を実装する必要はなく、Teams クライアントのキャリア サービスを受け取ることも可能です)。
- SBC を複数のテナントに接続します。
- PSTN サービスを顧客に提供します。
- 通話品質の終了を管理します。
- PSTN サービスに個別に料理。

Microsoft は、お使いのカーリヤーを管理しません。 Microsoft は、PBX (Microsoft 電話システム) と Teams クライアントを利用しています。 Microsoft は、電話と Microsoft 電話システムで使用できる SBC をサーティフトします。 このキャリアを選ぶ前に、選択した SBC がサーティファイドになっており、音声品質をエンドに管理できることを確認してください。

シナリオを構成するテクニカル実装手順は次のとおりです。

**Carrier のみ:**
1. SBC を展開し、認認された SBC ベンダーからの指示に従ってホスティング シ [ナリオ用に構成します](#deploy-and-configure-the-sbc)。
2. キャリア テナントで基本ドメイン名を登録し、ワイルドカードのチルドカードの明書を要求します。
3. base ドメインの一部であるすべての顧客のサブドメインを登録します。

**顧客グローバル管理者とのカタログ**
1. サブドメイン名を顧客テナントに追加します。
2. サブドメイン名をアクティブ化します。
3. 業者から顧客テナントにトランクを構成し、ユーザーをプロビジョニングします。

*Microsoft 365 または Office 365 の DNS の基礎とドメイン名の管理方法を Office理解してください。 [詳細に進む前に、Microsoft 365 または Office 365 のドメインに](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 関するヘルプを確認します。*

## <a name="deploy-and-configure-the-sbc"></a>SBC を展開および構成する

SBC ホスティング シナリオ用に SBC を展開して構成する方法の詳細な手順については、SBC ベンダーのドキュメントを参照してください。

- **AudioCodes:** [ダイレクト ルーティング構成ノート](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)、「オーディオコード SBC を Microsoft Teams Direct Routing Hosting Model 構成メモに接続しています」で説明されている SBC ホスティング シナリオの構成。 
- **または、直接**[ルーティング構成ノート](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)、SBC ホスティング シナリオの構成については、「Microsoft」セクションで説明します。 
- **リボンのコミュニケーション:** リボン コア[SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)とこのページ リボンのベスト プラクティスの構成方法に関するドキュメントについては、リボン コアの Microsoft Teams 構成ガイドを参照してください[- Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)用の通信事事カートの構成
- **TE-Systems (anynode):**  ドキュメントの [TE-Systems コミュニティ ページに登録](https://community.te-systems.de/) し、複数のテナントに関してどのノード SBC を構成する方法の例を参照してください。
- **メタッチ:**  複数のテナントで Perimeta SBC を有効にする方法については、ドキュメントのメタッチ コミュニ [ティ](https://sso.metaswitch.com/UI/Login) ページに登録してください。

> [!NOTE]
> 「連絡先」ヘッダーの構成方法についてはお支払いください。 [連絡先] ヘッダーは受信招待メッセージで顧客テナントを検索するために使用されます。 

## <a name="register-a-base-domain-and-subdomains"></a>基本ドメインとサブドメインを登録する

ホスティング シナリオでは、次を作成する必要があります。
- キャリアが所有する基本ドメイン名 1 つ。
- すべての顧客テナントの基本ドメイン名に含めたサブドメインです。

次の例では、次の例を参照してください。
- アドバタムとは、インターネットやテレフォニー サービスを用意することによって、複数の顧客を利用するキャリアです。
- Woodgrove Bank、Contoso、Adventure Works は 3 人の顧客であり、Microsoft 365 または Office 365 ドメインを持つが、アタムからテレフォニー サービスを受け取るお客様です。

サブドメインは **、Microsoft** 365 または Office 365 に招待状を送信するときに連絡先ヘッダーに設定されるトランクの FQDN 名と一致している必要があります。 

Microsoft 365 または Office 365 の直接ルーティング インターフェイスに通話が転送されると、インターフェイスでは連絡先ヘッダーを使用してユーザーが検索されるテナントを見つけます。 直接ルーティングでは、複数のテナントで重複できる DID 番号を持つ顧客もいます。 そのため、連絡先ヘッダーの FQDN 名は、電話番号でユーザーを検索する正しいテナントを特定する必要があります。

*Microsoft  [365 または 365 組織でのドメイン名の](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 作成の詳細については、「Office 365 ドメインのヘルプ Office」を参照してください。*

次の図は、基本ドメイン、サブドメイン、連絡先のヘッダーの要件をまとめたものです。

![ドメインと連絡先のヘッダーの要件を示す図](media/direct-routing-1-sbc-requirements.png)

SBC では接続を認証するには、サーティフェイスが必要です。 SBC ホスティングのシナリオでは、その配配会社は、SAN * \* .base_domain \* (.customers.adatum.biz など) での認明書を要求する必要があります*。 このこの接続は、1 つの SBC から提供される複数のテナントへの接続の認証に使用できます。


次の表は、構成の例です。


|新しいドメイン名 |種類|登録済み  |SBC 用の Certificate SAN  |例でのテナントの既定ドメイン  |ユーザーに通話を送信するときに、SBC が連絡先ヘッダーに表示される必要がある FQDN 名|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     キャリア テナントでは  |    \*.customers.adatum.biz  |   adatum.biz      |NA はサービス テナントであり、ユーザーは必要ありません |
|sbc1.customers.adatum.biz|    Subdomain  |    カスタマー テナント内  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain | カスタマー テナント内   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain | カスタマー テナント内 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

基本とサブドメインを構成するには、以下に示す手順に従ってください。 この例では、基本ドメイン名 (customers.adatum.biz) と、1 つのお客様 (Woodgrove Bank テナント内の sbc1.customers.adatum.biz) を構成します。

> [!NOTE]
> キャリsbcX.customers.adatum.biz テナントで音声を有効にするには、テナントを使用します。 sbcX には一意で有効な英数字ホスト名を使用できます。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>キャリア テナントで基本ドメイン名を登録する

**これらのアクションは、キャリア テナントで実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>キャリア テナントに適切な権限があることを確認する

新しいドメインの追加は、グローバル管理者として Microsoft 365 管理センターにサインインしている場合にのみ行います。 

役割を検証するには、Microsoft 365 管理センターにサインインし https://portal.office.com) ([ユーザー**Users**  >  **アクティブなユーザー] に移動**して、全体管理者ロールがあることを確認します)。 

管理者ロールと、Microsoft 365 または Office 365 でロールを割り当てる方法については、「Office 365 の管理者ロールについて [」を参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>テナントに基本ドメインを追加して確認する

1. Microsoft 365 管理センターで、[セットアップ ドメインの**追加**  >  **]**  >  **に移動します**。
2. 所有 **しているドメインの入力ボックス** に、基本ドメインの FQDN を入力します。 次の例では、基本ドメインは*ネームcustomers.adatum.biz。*

    ![[ドメインの追加] ページが表示されたスクリーンショット](media/direct-routing-2-sbc-add-domain.png)

3. **[次へ]** をクリックします。
4. この例では、テナントは既に検証済adatum.bizドメイン名として既に設定されています。 ウィザードでは、登録済みの名前のサブドメインであるcustomers.adatum.biz追加の確認を求められることはありません。 ただし、以前に確認されていない FQDN を追加した場合は、確認プロセスを実行する必要があります。 次に確認のプロセス [を示します](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![確認済みドメイン名の確認を示すスクリーンショット](media/direct-routing-3-sbc-verify-domain.png)

5. [ **次へ**] をクリックし **、[DNS 設定の更新]** ページで **自分で DNS** レコードを追加して、[次へ] をクリック **します**。
6. 次のページで、(Exchange、SharePoint、Teams/Skype for Business のドメイン名を使用する場合を含む場合を含む場合を含む) すべての値をクリアし、[次 **へ]** をクリックして、[完了] をクリック **します**。 セットアップ完了の状態で新しいドメインが表示されていることを確認します。

    ![セットアップが完了した状態のドメインを示すスクリーンショット](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>ドメイン名をアクティブ化する

ドメイン名を登録した後は、E1、E3、E5 ライセンスを持つユーザーを 1 つ以上追加し、作成した基本ドメインに一致する SIP アドレスの FQDN 部分で SIP アドレスを割り当てて、ライセンス認証する必要があります。 ドメインのライセンス認証後にライセンスを再び取得できます (最大 24 時間かかる場合があります)。

*Microsoft [365 または Office 365 の組織でのユーザーの](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 追加の詳細については、「Microsoft 365 または Office 365 ドメインのヘルプ Officeを参照してください」を参照してください。*

例 test@customers.adatum.biz:

![基本ドメインのライセンス認証ページのスクリーンショット](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>顧客テナントでサブドメイン名を登録する

顧客ごとに一意のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名をsbc1.customers.adatum.bizテナント内にサブドメインを作成woodgrovebank.us。

**次のすべての操作は、顧客テナントにあります。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>顧客テナントに適切な権限があることを確認する

新しいドメインの追加は、グローバル管理者として Microsoft 365 管理センターにサインインしている場合にのみ行います。 

役割を検証するには、Microsoft 365 管理センターにサインインし https://portal.office.com) ([ユーザー**Users**  >  **アクティブなユーザー] に移動**して、全体管理者ロールがあることを確認します)。 

管理者ロールと、Microsoft 365 または Office 365 でロールを割り当てる方法については、「Office 365 の管理者ロールについて [」を参照してください](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>顧客テナントにサブドメインを追加して確認する
1. Microsoft 365 管理センターで、[セットアップ ドメインの**追加**  >  **]**  >  **に移動します**。
2. 所有している **ドメインを入力** して、このテナントのサブドメインの FQDN を入力します。 下の例では、サブドメインは参照sbc1.customers.adatum.biz。

    ![[ドメインの追加] ページのスクリーンショット](media/direct-routing-5-sbc-add-customer-domain.png)

3. **[次へ]** をクリックします。
4. FQDN はテナントに登録されることはありません。 次の手順では、ドメインを確認する必要があります。 [ **代わりに TXT レコードを追加する] を選択します**。 

    ![[ドメインの確認] ページのスクリーンショット](media/direct-routing-6-sbc-verify-customer-domain.png)

5. [ **次へ**] をクリックし、生かす TXT 値をメモしてドメイン名を確認します。

    ![[ドメインの確認] ページのテキスト レコードのスクリーンショット](media/direct-routing-7-sbc-verify-domain-txt.png)

6. キャリアの DNS ホスティング プロバイダーで前の手順の値を使用して TXT レコードを作成します。

    ![TXT レコードの作成を示すスクリーンショット](media/direct-routing-8-sbc-txt-record.png)

    詳細については、任意の [DNS ホスティング プロバイダーで DNS レコードを作成してください](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 顧客の Microsoft 365 管理センターに戻り、[確認] を **クリックします**。 
8. 次のページで **、[DNS レコードを自分** で追加する] を選び、[次へ] を **クリックします**。

    ![[DNS 設定を更新する] ページのオプションのスクリーンショット](media/direct-routing-9-sbc-update-dns.png)

9. [オンライン サービス **の選択] ページで** 、[すべてのオプションをオフにし、[次へ] を **クリックします**。

    ![[オンライン サービスの選択] ページのスクリーンショット](media/direct-routing-10-sbc-choose-services.png)

10. [DNS **設定** の **更新] ページで [完了] をクリック** します。

    ![[DNS 設定を更新する] ページのスクリーンショット](media/direct-routing-11-sbc-update-dns-finish.png)

11. 状態がセットアップされている **ことを確認します**。 
    
    ![セットアップが完了した状態を示すページのスクリーンショット](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>サブドメイン名をアクティブ化する

ドメイン名を登録した後は、1 人以上のユーザーを追加してアクティブにし、顧客テナントの作成済みサブドメインに一致する SIP アドレスの FQDN 部分を使用して SIP アドレスを割り当てる必要があります。 サブドメインのライセンス認証後に、ユーザーからライセンスを再び復元できます (最大 24 時間かかる場合があります)。

*Microsoft [365 または Office 365 の組織でのユーザーの](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 追加の詳細については、「Microsoft 365 または Office 365 ドメインのヘルプ Officeを参照してください」を参照してください。*

たとえば、次のように test@sbc1.customers.adatum.bizします。

![サブドメイン ページのライセンス認証ページのスクリーンショット](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクとプロビジョニング ユーザーを作成する

直接ルーティングのまったくリリースでは、New-CSOnlinePSTNGateway を使用して、各サーバス テナント (顧客テナント) にトランクを追加する必要があります。

ただし、次の 2 つの理由で、これが最適化されていません。
 
- **オーバーヘッド管理**。 たとえば、メディア バイパスの有効化や無効化などの一部のパラメーターを変更します。 ポートを変更するには (Set-CSOnlinePSTNGateway を実行して) 複数のテナントのパラメーターを変更する必要がありますが、実は同じ SBC です。 

-  **オーバーヘッドの処理**。 正常性データの収集とモニタリング - 同じ SBC と同じ子トランクから収集される SIP オプションは、同じ SBC と同じ医的トランクから収集され、ルーティング データの処理が遅くなります。
 
このフィードバックに基づき、Microsoft は新しいロジックを使用して、お客様のテナントのトランクをプロビジョニングしています。

新しいエンティティが 2 つ追加されました。
-    コマンド New-CSOnlinePSTNGateway コマンド New-CSOnlinePSTNGateway コマンドを使用して Carrier テナントに登録されたカラーのトランク (例: New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true)

-    登録を必要としないデタイティブトトランク。 これは、キャリアのトランクから追加する必要のないホスト名にすぐです。 キャリア トランクからのすべての構成パラメーターを示します。 PowerShell では、デイナリティブトトを作成する必要はありません。また、キャリアのトランクとの関連付けは FQDN 名に基づきます (以下の詳細を参照)。

**プロビジョニング ロジックと例**

-    キャリアは、Set-CSOnlinePSTNGateway コマンドを使用して、1 つのトランク (カーライヤー ドメインのトランク) のセットアップと管理のみが必要です。 上の例では、数式はadatum.biz;
-    顧客テナントでは、キャリアは、デベロッパーがデベロッパーのトランクの FQDN をユーザーのボイス ルーティング ポリシーに追加するだけでした。 新しい CSOnlinePSTNGateway をトランク用に実行する必要はありません。
-    名前の候補として、名前の候補として、カーニング トランクからすべての構成パラメーターを取り出したり、ディネティブを引き出したりします。 例:
-    Customers.adatum.biz– ケーブリッパー のテナントで作成する必要があるキャリスクを確認します。
-    Sbc1.customers.adatum.bizドセットされたお客様のテナントで、PowerShell で作成する必要がない場合は、ダイナリングされたトランクを指定します。  オンライン のルーティング ポリシーの顧客テナントで、ダイヤルトのダイヤルトの名前を追加するだけで、作成できます。
-   Carrier は、ドライブのトランク FQDN を Carrier SBC ip アドレスに解決するために DNS レコードをセットアップする必要があります。

-    キャリア トランクで行われた変更はすべて自動的に挿入されたトランクに自動的に適用されます。 たとえば、表者は、カーキャリアのトランクで SIP ポートを変更でき、この変更はすべてのダイヤルドトランクに適用されます。 トランクを構成する新しいロジックを構成する新しいロジックは、すべてのテナントに移動する必要がないため、トランクごとにパラメーターを変更する必要がないので、管理を簡素化します。
-    オプションは、カートリのトランク FQDN にのみ送信されます。 キャリアトトの正常性の状態はすべてのダイヤルクに適用され、ルーティングの決定に使用されます。 Direct ルーティングの [オプションの詳細について説明します](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。
-    キャリアは、キャリアトをドレンダリングでき、すべてのダイヤルクが下書きされます。 
 

**前のモデルからカーリヤーのトランクへの移行**
 
キャリア ホストモデルの現在の実装から新しいモデルへの移行については、その業者はお客様のテナントのトランクを再構成する必要があります。 Remove-CSOnlinePSTNGateway を使用して顧客テナントからトランクを削除します (キャリア テナントにトランクを付けます)。

キャリアとドニック モデルを使用してプロビジョニングとプロビジョニングを強化する予定ですので、できるだけ新しいソリューションへの移行を強くお奨ちします。
 

連絡先ヘッダーでサブドメインの FQDN 名を送信する場合の [SBC](#deploy-and-configure-the-sbc) ベンダーの手順を参照してください。

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>テナント フェールオーバーの設定に関する考慮事例 

マルチテナント環境のフェールオーバーを設定するには、次の操作を行う必要があります。

- テナントごとに、2 つの異なる SBC 用の FQDN を追加します。  次に例を示します。

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- ユーザーのオンライン ボイス ルーティング ポリシーで、両方の SBC を指定します。  一致する SBC が失敗した場合、ルーティング ポリシーは 2 番目の SBC に通話を転送します。


## <a name="see-also"></a>関連項目

[ダイレクト ルーティングを計画する](direct-routing-plan.md)

[ダイレクト ルーティングを構成する](direct-routing-configure.md)

