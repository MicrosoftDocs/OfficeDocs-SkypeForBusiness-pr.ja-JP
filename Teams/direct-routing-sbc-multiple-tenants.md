---
title: 複数のテナントのセッション ボーダー コント ローラーを構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: 複数のテナントを処理する 1 つのセッション ボーダー コント ローラー (SBC) を構成する方法について説明します。
ms.openlocfilehash: 3073800a6c200bcaeffafb557d6ea149dee598cd
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866460"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>複数のテナントのセッション ボーダー コント ローラーを構成します。

直接ルーティングでは、構成する 1 つセッション ボーダー コント ローラー (SBC) 複数のテナントを処理するをサポートします。

> [!NOTE]
> マイクロソフト パートナーまたは PSTN 通信事業者、このドキュメントの後半には、通信事業者と呼ばれるは、このシナリオは設計されています。 キャリアは、お客様に、マイクロソフトのチームに配信されるテレフォニー サービスを販売しています。 

キャリア。
- SBC のデータ センターでの管理を展開し、(お客様が、SBC を実装する必要はありませんし、チームのクライアントでのキャリアからテレフォニー サービスを受信する)。
- 複数のテナントに SBC を相互接続します。
- PSTN サービスを提供しています。
- エンド ツー エンドの通話品質を管理します。
- PSTN サービスに対して個別に請求します。

マイクロソフトでは、通信事業者は管理されません。 マイクロソフトは、PBX (マイクロソフトの電話システム) とチームのクライアントを提供しています、電話かを確認して、SBCs マイクロソフトの電話システムで使用できるかを確認します。 配送業者を選択するには、前にある選択認定 SBC があり、エンド ツー エンドの音声品質を管理することができますを確認してください。

シナリオを構成するのには技術的な実装手順を次に示します。

**キャリアのみ。**
1. SBC を配置し、[認定の SBC ベンダーの指示](#deploy-and-configure-the-sbc)に従って、ホストのシナリオ用に構成します。
2. キャリア テナントでベースのドメイン名を登録し、ワイルドカード証明書を要求します。
3. ベースのドメインの一部であるすべてのお客様のサブドメインを登録します。

**キャリアでは、お客様のグローバル管理者:**
1. お客様のテナントには、サブドメイン名を追加します。
2. サブドメイン名を有効にします。
3. お客様のテナントとプロビジョニングのユーザーに、キャリアからトランクを構成します。

*DNS の基礎と Office 365 でドメイン名を管理する方法を理解することを確認してください。進む前に[Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を確認してください。*

## <a name="deploy-and-configure-the-sbc"></a>展開し、SBC を構成します。

展開し、SBC ホスティング シナリオでは、半角を構成する方法の詳細な手順については、SBC の製造元のマニュアルを参照してください。

- **は:**[直接ルーティングの構成に関する注意事項](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)」の接続は SBC マイクロソフト チーム直接ルーティングのホスティング モデル構成メモにします」で説明したシナリオをホストしている SBC の構成 
- **通信のリボン:** シナリオをホストしている SBC、コア ・ シリーズのみがサポートされています。 [リボン通信 SBC コア Microsoft チーム構成ガイド 』](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)を参照してください。

> [!NOTE]
> 「連絡先」ヘッダーを構成する方法に注意してください。 Contact ヘッダーを使用して、招待の受信メッセージにお客様のテナントを検索します。 

## <a name="register-a-base-domain-and-subdomains"></a>基本ドメインとサブドメインを登録します。

ホスティングのシナリオでは、作成する必要があります。
- 配送業者が所有する 1 つのベースのドメイン名です。
- サブドメインで顧客のすべてのテナント ベースのドメイン名の一部であります。

次の例ではします。
- Adatum は、インターネットおよびテレフォニー サービスを提供することで複数の顧客サービスを提供するキャリアです。
- Woodgrove Bank、contoso 社では、Adventure Works は、Office 365 のドメインが存在するが、Adatum からテレフォニー サービスを受信する 3 つの顧客です。

サブドメインに**する必要があります**では、Office 365 に招待状を送信するときに、顧客および取引先担当者のヘッダー内の FQDN を構成するトランクの FQDN 名と一致します。 

Office 365 の直接のルーティング インターフェイスでの呼び出しが到着すると、インタ フェースは、テナントのユーザーを検索する必要がありますを検索するのに連絡先ヘッダーを使用します。 直接ルーティングの使用しない電話番号をルックアップへの招待は、一部のお客様がない必要がありますように番号がいくつかのテナントが重複することにしました。 したがって、電話番号で、特定のユーザーを検索するのには正確なテナントは Contact ヘッダー内の FQDN 名が必要です。

*Office 365 テナントにドメイン名を作成する方法の詳細については、 [Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*

次の図は、基本ドメイン、サブドメインでは、連絡先のヘッダーの要件をまとめたものです。

![ベースのドメイン、サブドメインでは、連絡先のヘッダーの要件](media/direct-routing-1-sbc-requirements.png)

SBC には、接続の認証に証明書が必要です。 キャリアは SBC のホスティング シナリオでは、san 証明書を要求する必要があります*\*.base_domain (たとえば、 \*customers.adatum.biz)*。 この証明書は、複数のテナントが 1 つの SBC からへの接続を認証するために使用できます。

次の表は、1 つの構成の例です。


|新しいドメイン名 |種類|登録  |SBC の SAN 証明書  |テナントの既定のドメインの例  |ユーザーへの呼び出しを送信するとき、連絡先のヘッダーに SBC が提示しなければならない FQDN 名|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    ベース     |     キャリアのテナントで  |    \*。 customers.adatum.biz  |   adatum.biz      |「Na」と、これは、サービス テナント ユーザーは存在しません |
|sbc1.customers.adatum.biz|    サブドメイン  |    お客様のテナントで  |    \*。 customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   サブドメイン | お客様のテナントで   |   \*。 customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   サブドメイン | お客様のテナントで |   \*。 customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

ベースおよびサブドメインを構成するには、以下に示す手順に従ってください。 例では、ベースのドメイン名 (customers.adatum.biz) と 1 つの顧客 (sbc1.customers.adatum.biz では、Woodgrove Bank のテナント) 用のサブドメイン構成します。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>キャリア テナントでベースのドメイン名を登録します。

**キャリアのテナントでは、これらのアクションが実行されます。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>キャリア テナント内の適切な権限があることを確認します。

大域管理者として Office 365 管理センターにサインインする場合にのみ、新しいドメインを追加できます。 

ある役割を検証するにサインインしてください Microsoft 365 の管理センター (https://portal.office.com)**ユーザー**には、 > **アクティブなユーザー**、グローバル管理者ロールがあることを確認します。 

管理者の役割と Office 365 のロールを割り当てる方法の詳細については、 [Office 365 の管理者の役割](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)を参照してください。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>テナント ベースのドメインを追加し、そのことを確認

1.  Microsoft 365 管理センターでは、**セットアップ**に移動 > **ドメイン** > **ドメインを追加**します。
2.  **自分が所有するドメインを入力してください**] ボックスで、ベースのドメインの FQDN を入力します。 次の例では、ベースのドメインとは、 *customers.adatum.biz*です。

    ![ベースのドメインを追加します。](media/direct-routing-2-sbc-add-domain.png)

3. [**次へ**] をクリックします。
4. 例では、テナントは既に検証済みのドメイン名として adatum.biz を持っています。 ウィザードは要求されません追加の検証 customers.adatum.biz が既に登録されている名前のサブドメインであるためです。 ただし、前に確認されていませんが、FQDN を追加する場合は、検証のプロセスを経由する必要があります。 検証のプロセスでは、[以下に説明](#add-a-subdomain-to-the-customer-tenant-and-verify-it)します。

    ![確認ドメイン名の確認](media/direct-routing-3-sbc-verify-domain.png)

5.  [**次へ**] をクリックし、[ **DNS の設定の更新**] ページで、 **DNS レコードを自分で追加します**を選択して [**次へ**] をクリックします。
6.  [次へ] ページですべての値をオフに場合を除き、ビジネスの交換方法、SharePoint、またはチームと Skype のドメイン名を使用するには)、[**次へ**] をクリックし、 **[完了**] をクリックします。 セットアップの完了状態では、新しいドメインを確認します。

    ![ドメインの完全なセットアップのステータスを表示](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>ドメイン名を有効化します。

ドメイン名を登録した後、少なくとも 1 人のユーザーを追加することによってアクティブ化し、作成した基本ドメインと一致する SIP アドレスの FQDN の部分での SIP アドレスを割り当てる必要があります。

*Office 365 テナントのユーザーの追加の詳細については、 [Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*

例: test@customers.adatum.biz

![基本ドメインのアクティブ化ページ](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>お客様のテナントにサブドメイン名を登録します。

すべてのお客様の固有のサブドメイン名を作成する必要があります。 この例では、既定のドメイン名 woodgrovebank.us のテナントにサブドメインの sbc1.customers.adatum.biz を作成します。

**お客様のテナントには、以下のすべてのアクションです。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>お客様のテナント内の適切な権限があることを確認します。

大域管理者として Office 365 管理センターにサインインする場合にのみ、新しいドメインを追加できます。 

ある役割を検証するにサインインしてください Microsoft 365 の管理センター (https://portal.office.com)**ユーザー**には、 > **アクティブなユーザー**、グローバル管理者ロールがあることを確認します。 

管理者の役割と Office 365 のロールを割り当てる方法の詳細については、 [Office 365 の管理者の役割](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)を参照してください。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>お客様のテナントにサブドメインを追加して、そのことを確認
1. Microsoft 365 管理センターでは、**セットアップ**に移動 > **ドメイン** > **ドメインを追加**します。
2. **自分が所有するドメインを入力してください**] ボックスには、このテナントのサブドメインの FQDN を入力します。 次の例では、サブドメインとは、sbc1.customers.adatum.biz です。

    ![お客様のサブドメインを追加します。](media/direct-routing-5-sbc-add-customer-domain.png)

3. [**次へ**] をクリックします。
4. テナントの FQDN が登録されたことはありません。 次の手順でドメインを確認する必要があります。 **代わりに TXT レコードを追加する**を選択します。 

    ![[ドメインの確認] ページのオプション](media/direct-routing-6-sbc-verify-customer-domain.png)

5. [**次へ**] をクリックし、ドメイン名を確認するのには生成されたテキスト値を確認します。

    ![[ドメインの確認] ページのテキスト レコード](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 配送業者の DNS ホスティング プロバイダーの前の手順からの値は、TXT レコードを作成します。

    ![配送業者の DNS ホスティング プロバイダーで TXT レコードを作成します。](media/direct-routing-8-sbc-txt-record.png)

    詳細については、 [Office 365 のすべての DNS ホスティング プロバイダーを作成する DNS レコード](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)を参照してください。

7. お客様の Microsoft 365 管理センターに戻るし、[**確認**] をクリックします。 
8. [次へ] ページでは、 **DNS レコードを自分で追加します**を選択し、[**次へ**] をクリックします。

    ![DNS の更新の設定] ページのオプション](media/direct-routing-9-sbc-update-dns.png)

9. **オンライン サービスの選択**] ページで、[すべてのオプションをオフにし、[**次へ**] をクリックします。

    ![オンライン サービス ページの選択]](media/direct-routing-10-sbc-choose-services.png)

10. **DNS の更新の設定**] ページで [**完了**] をクリックします。

    ![DNS の更新の設定] ページ](media/direct-routing-11-sbc-update-dns-finish.png)

11. 状態で**セットアップを完了**を確認します。 
    
    ![完全なセットアップのステータスを表示するページ](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>サブドメイン名をアクティブにします。

ドメイン名を登録した後には、少なくとも 1 人のユーザーを追加することによってアクティブ化し、お客様のテナントで作成したサブドメインに一致する SIP アドレスの FQDN の部分での SIP アドレスを割り当てる必要があります。

*Office 365 テナントのユーザーの追加の詳細については、 [Office 365 のドメイン関連のヘルプ](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)を参照してください。*

例: test@sbc1.customers.adatum.biz

![サブドメインのページのアクティブ化](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>トランクとプロビジョニングのユーザーを作成します。

> [!NOTE]
> 技術の採用プログラムで受信したフィードバックに基づき、マイクロソフトは、プロセスを簡素化するお客様のテナントのトランクを作成するプロセスを変更できます。 このページのドキュメントの更新を監視し、次の詳細についてはマイクロソフト テクニカル コミュニティ ブログしてください。 

新しい CSonlinePSTNGateway コマンドを使用して顧客のドメインには、トランクを作成します。 トランクの FQDN が**必要**では、顧客用に作成されたサブドメインと一致します。

例:

*新しい-CSOnlinePSTNGateway-FQDN sbc1.customers.adatum.biz SipSignallingPort 5068*

電話番号を持つユーザーをプロビジョニングし、音声のルーティングを構成します。

新規の CSOnlinePSTNGateway の詳細については、ユーザーのプロビジョニングと、音声のルーティングを構成するを参照してください[直接ルーティングを構成](direct-routing-configure.md)します。


サブドメインの FQDN 名を送信する連絡先のヘッダーに設定する方法についての[SBC の製造元の指示](#deploy-and-configure-the-sbc)を参照してください。

