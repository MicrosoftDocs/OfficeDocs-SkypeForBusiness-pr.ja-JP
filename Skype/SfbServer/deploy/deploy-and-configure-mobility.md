---
title: 展開し、Skype のビジネスのサーバーの移動を構成します。
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この資料でを Skype ビジネス サーバー移動機能を利用できるモバイル デバイスをできるように、モバイル サービスを使用するビジネスのサーバーのインストールに既存の Skype を構成する手順を説明します。
ms.openlocfilehash: e1799459d2e7723298aa7fdda17f89a9041efd15
ms.sourcegitcommit: e93b12f5ebaad1140d7df798b5e0647197b9213d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2018
ms.locfileid: "26649716"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>展開し、Skype のビジネスのサーバーの移動を構成します。  
 
この資料でを Skype ビジネス サーバー移動機能を利用できるモバイル デバイスをできるように、モバイル サービスを使用するビジネスのサーバーのインストールに既存の Skype を構成する手順を説明します。
  
[Skype ビジネス サーバーの移動の計画](../plan-your-deployment/mobility.md)の資料を確認し、する必要がありますビジネス サーバー環境で、Skype にモビリティを展開する次の手順を続行する準備ができました。 手順は次のとおりです (この表には許可一覧も含めます)。
  
|**段階**|**アクセス許可**|
|:-----|:-----|
|
            「[DNS レコードの作成](deploy-and-configure-mobility.md#CreateDNSRec)」 <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[証明書を変更する](deploy-and-configure-mobility.md#ModCerts) <br/> |ローカル管理者  <br/> |
|[リバース プロキシを構成する](deploy-and-configure-mobility.md#ConfigRP) <br/> |ローカル管理者  <br/> |
|[ハイブリッド展開でのモビリティの自動検出を構成する](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[モビリティ展開をテストする](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[プッシュ通知を構成する](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[モビリティ ポリシーを構成する](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
次のすべてのセクションには、計画トピックを読んでいることが前提となる手順が含まれています。

> [!NOTE]
> 従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。 ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。 MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="create-dns-records"></a>DNS レコードの作成
<a name="CreateDNSRec"> </a>

ビジネス サーバー環境で、Skype の一部としてこれらを既に必要がありますが、操作する自動検出のための次のレコードを作成する必要があります。
  
- 組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード。
    
- 組織のネットワーク外から接続するモバイル ユーザーをサポートするための外部 (またはパブリック) DNS レコード。
    
これらのレコードは、A (ホスト) 名または CNAME のどちらかにできます (両方作成する必要はなく、すべての手順がここに含まれています)。
  
### <a name="create-an-internal-dns-cname-record"></a>内部 DNS CNAME レコードを作成する

1. **Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。
    
2. [**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。
    
3. コンソール ウィンドウの左側のペインでは、ドメインに移動する必要がありますのビジネス サーバーのフロント エンド サーバーでは、Skype をホームし、が**前方参照ゾーン**] を展開します。
    
4. 次のどちらがあるか確認します。
    
   - (標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。
    
   - 任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。
    
5. 判別できたら SIP ドメイン名を右クリックしてから、[**新しいエイリアス (CNAME)**] をメニューから選択します。
    
6. [**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。
    
7. **完全修飾ドメイン名 (ターゲットのホストに対して FQDN を**をフロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上記の手順 4 で特定の内部の Web サービスの FQDN を入力または参照する必要があります。 入力したら、[OK] をクリックします。
    
8. ビジネス サーバー環境に、Skype でサポートされている各 SIP ドメインの前方参照ゾーンに新しい自動検出の CNAME レコードを作成する必要があります。
    
### <a name="create-an-external-dns-cname-record"></a>外部 DNS CNAME レコードを作成する

1. ご利用のパブリック DNS プロバイダーが分かりませんので、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。
    
2. この時点では、SIP ドメインは既に存在してある Skype のビジネス サーバーの。 この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。
    
3. 次のどちらがあるか確認します。
    
   - (標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。
    
   - 任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。
    
4. その情報が得られたら、[**新しいエイリアス (CNAME)**] の作成オプションを選択することができます。
    
5. [**エイリアス名**] を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。
    
6. 次に**ターゲット ・ ホストの FQDN**を入力する領域が存在する必要があります、これは、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上記の手順 3 で特定の FQDN を指定する必要があります。
    
7. ここでは、保存する必要があります。 またはビジネス サーバー環境に、Skype では、各 SIP ドメインの前方参照ゾーンに追加の CNAME レコードを作成する場合は、する必要がありますが、あなたが準備ができて、作業内容を保存します。
    
### <a name="create-an-internal-dns-a-record"></a>内部 DNS A レコードを作成する

1. **Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。
    
2. [**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。
    
3. コンソール ウィンドウの左側のペインでは、ドメインに移動する必要がありますのビジネス サーバーのフロント エンド サーバーでは、Skype をホームし、が**前方参照ゾーン**] を展開します。
    
4. 次のどちらがあるか確認します。
    
   - (標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。
    
   - 任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。
    
5. 判別できたら SIP ドメイン名を右クリックしてから、[**新しいホスト (A または AAAA)**] をメニューから選択します。
    
6. [**名前**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。
    
7. [ **IP アドレス**] ボックスで、上記の手順 4 では、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、内部の Web サービスの IP アドレスの種類が識別されます。
    
8. 入力したら [**ホストの追加**] をクリックしてから [**OK**] をクリックします。
    
9. ビジネス サーバー環境に、Skype でサポートされている各 SIP ドメインの前方参照ゾーンで新しいの自動検出の A または AAAA レコードを作成する必要があります。 これを行うには手順 6 - 8 を必要な回数繰り返します。
    
10. 終了したら [**完了**] をクリックします。
    
### <a name="create-an-external-dns-a-record"></a>外部 DNS A レコードを作成する

1. ご利用のパブリック DNS プロバイダーがわからないため、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。
    
2. この時点では、SIP ドメインは既に存在してある Skype のビジネス サーバーの。 この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。
    
3. 次のどちらがあるか確認します。
    
   - (標準またはエンタープライズ) のフロント エンド サーバーまたはフロント エンド プールのホスト A または AAAA レコードです。
    
   - 任意のホスト A または AAAA レコード ディレクターまたはディレクター プールの (省略可能な構成で展開する必要があります)。
    
4. その情報が得られたら、[**新しいホスト A または AAAA**] の作成オプションを選択することができます。
    
5. **エイリアス名**を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。
    
6. 次の**IP アドレス**を入力する領域が存在する必要があります、これは、フロント エンド プールまたは 1 つのフロント エンド サーバーまたはディレクター プール (ディレクター)、上の手順 3 で特定の ip アドレスを指定する必要があります。
    
7. ここでは、保存する必要があります。 または追加作成する必要がある場合 A または AAAA レコード各 SIP ドメインの前方参照ゾーンで、Skype をビジネスのサーバー環境のを行う必要がありますが、1 回の準備が整ったら、作業を保存します。
    
## <a name="modify-certificates"></a>証明書を変更する
<a name="ModCerts"> </a>

証明書に関する計画についての疑問があれば、私たちしたを資料に記載されて、 [Skype のビジネス サーバーの移動を計画](../plan-your-deployment/mobility.md)します。 それを読んだ後で、以下の点を説明します。
  
- 新しい証明書が必要か。
    
- 認証局 (CA) に新しい証明書を申請する。
    
- PowerShell を使用して、使用中の証明書をアップグレードする。
    
- Microsoft 管理コンソール (MMC) で証明書スナップインを使用して証明書を確認しています。
    
### <a name="do-i-need-new-certificates"></a>新しい証明書が必要か。

1. まず使用中の証明書の内容を確認して、必要とするエントリーの有無を調べる必要があります。 ローカル管理者であるアカウントを使用してビジネス サーバー、Skype にログインする必要があります。 このアカウントには、手順中のいくつかで認証局 (CA) の発行権限も必要とされます。
    
2. ビジネス サーバー管理シェルには (場合は、[スタート] メニューまたはタスク バーに固定されていることがあるないことを検索する検索を使用できます)、Skype を開きます。
    
3. 更新された証明書の追加を行う前に、すでに付与されている証明書の内容を知っておくことが重要となります。コマンドで次のように入力します。
    
   ```
   Get-CsCertificate
   ```

4. 手順 3 で得られた情報は固有の内容です。内容を吟味して、複数のことに対して単一の証明書が付与されているのか、それとも証明書を必要とする別々のコンポーネントに別の証明書が付与されているのか判断します。**Use** パラメーターを使用すれば、証明書がどのように使われているかが分かり、**Thumbprint** パラメーターを使用すれば、証明書が同一か別々かが分かります。
    
5. 計画セクションで推奨されている SAN エントリーがあれば、申し分ありません。ない場合は、新規の証明書を 1 つ または複数の証明書を認証局に申請する必要があります (構成に依存します)。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>認証局 (CA) に新しい証明書を申請する。

1. あるどのような SAN エントリを参照するを確認して後、知っている (確認後上記の手順を使用して)、**単一の証明書**があるし、する必要があるすべてのエントリがないと説明しました。 新しい証明書要求を CA になる必要があります。 ビジネス サーバー PowerShell の Skype を開きます。
    
   - 欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - ここで、複数の SIP ドメインがあれば、上記の例に示すように AllSipDomain パラメーターを使うことはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 一例として次のようになります (-Ca パラメーターを自分の認証局パスで置き換える)。
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. または、必要なすべてのエントリがない**複数の証明書**があるが見つかりましたが、どのような SAN エントリを参照するを確認して後、。 新しい証明書要求を CA になる必要があります。 ビジネス サーバー PowerShell の Skype を開きます。
    
   - 欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - ここで、複数の SIP ドメインがあれば、上記の例に示すように AllSipDomain パラメーターを使うことはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 次のような例になります (-Ca パラメーターを自分の認証局パスで置き換える)。
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA により新しい証明書が作成されたら、それを割り当てる必要があります。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して証明書を割り当てる

- 「新しい証明書が必要か」のセクションで判明した内容に応じて、次のうちの**いずれか 1 つ**を実行する必要があります。
    
  - すべてに対して単一の証明書しかない (どの thumbprint も同じ) 場合、これを実行します。
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 別々の証明書が付与されている (thumbprint が異なる) 場合、代わりにこれを実行します。
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Microsoft 管理コンソール (MMC)

1. MMC の証明書スナップインを使用して、証明書を調べるオプションを利用します。検索に MMC と入力すれば、アプリケーション オプションのようにポップアップします。
    
2. 証明書スナップインを追加するには、「**ファイル**] をクリックしてから [**スナップインの追加と削除...**] をクリックします (またはキーボード ショートカット **Ctrl+M** を利用してもよい)。 **証明書** が左側のウィンドウにオプションとして表示されるので、それを選択してから、ポップアップ ウィンドウで [**コンピュータ アカウント**] を選択し、[**次へ**] をクリックします。
    
3. まだポップアップ ウィンドウの中で、おそらく調べたい証明書が所属しているコンピュータ上で作業を行っているはずなので、そうであれば選択されている [**ローカル コンピュータ**] のままにします。 リモート マシンで作業を行っている場合は、ラジオ ボタンを [**別のコンピュータ**] に切り替え、そのコンピュータの QFDN を入力するか、[**参照**] ボタンを使用して AD 内でそのコンピュータを探します。 コンピューターを選択すると、準備ができたら、[**終了**して [ **ok]** MMC にスナップインを追加する] をクリックする必要があります。
    
4. MMC の左側のペインで [**証明書**] セクションを展開します。 [**個人**] フォルダーも展開して、[**証明書**] を選択します。 これでこのストアにある証明書を見ることができます。
    
5. 表示したい証明書の場所を探すには、証明書を右クリックし、[**開く**] を選択します。
    
    > [!NOTE]
    > 知るには、どのような証明書ですか。 いずれか、単一の証明書をファームのすべてのものに割り当てられている必要があります別など、既定値、内部の Web サービスなどの複数の証明書がある場合があります、場合に複数の証明書を確認する必要があります。 複数の証明書は、同じ拇印があります。 
  
6. **証明書** ビューが表示されたら、[**詳細**] を選択します。そこで [**サブジェクト**] を選択すると、証明書のサブジェクト名が表示され、付与されたサブジェクト名と関連プロパティが表示されます。
    
7. **サブジェクトの別名**エントリーも確認する必要があります。次のうちの 1 つまたは複数が見つかります。
    
   - このプールは、プールの名前またはこの場合は、単一のサーバー名は、プールにはありません。
    
   - 証明書が割り当てられるサーバーの名前
    
   - 簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)
    
   - Web サービスの内部、および Web サービス外部の名前 (たとえば、webpool01.contoso.net、webpool01.contoso.com)、選択した内容に基づいてトポロジ ビルダーと Web サービスの選択を無効にします。
    
   - 既に割り当てられている場合、lyncdiscover。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。
    
     割り当てられている証明書が 2つ以上の場合は、それらを確認する必要があります (上記の注記を参照)。
    
8. したがってには、lyncdiscover を検索する場合。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコードを既に手に既に構成されているこの。 MMC を終了します。
    
9. これらが割り当てられていない場合は、新しい証明書を申請するか (上記で概説)、これらをポストリクエストでインストールする必要があります (次の PowerShell を推奨)。
    
## <a name="configure-the-reverse-proxy"></a>リバース プロキシを構成する
<a name="ConfigRP"> </a>

次の手順は、そのとおりに実行するように意図されたものではありません。と言うのは、製品の前のバージョンで、たとえば Threat Management Gateway (TMG) の構成について順を追って手順を説明しました。これを使用していないのであれば、自分のバージョンではそこから仕上げる必要があります。
  
TMG は Microsoft からはもはや製品として提供されておらず、その構成を行う必要があれば、「[Lync Server 2013 手順](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)」を調べることができます。 次の情報はのすべてのリバース プロキシが特定のチュートリアルの手順を提供できる方法がない場合でもより一般的には役に立つを目的としています。
  
検討すべき重要な事柄が 2 つあります。
  
- 最初の自動検出申請を HTTPS で行いますか (それを推奨しています)。
    
  - Web 公開ルールがある場合、それを変更する必要がありますか。
    
  - まだ Web 公開ルールがないのであれば、それを作成する必要があります。
    
- 最初の自動検出申請を HTTPS で行うのであれば、規則の作成や変更も必要となります。
    
> [!NOTE]
> **重要です**プロキシ タイムアウト値は、配置から配置に変化する番号です。 展開の監視では、クライアントの値を変更してください。 値を 200 程度に設定することができます。 環境内で Lync モバイル クライアントをサポートしている場合は、900 のタイムアウト値を持つ、Office 365 からプッシュ通知のタイムアウトを許可する 960 に値を設定してください。 クライアントを避けるためにタイムアウト値を大きく必要がある可能性があります切断の値が低すぎる、または数を減らす場合は、プロキシ経由での接続が切断されないが、クライアントが切断された後に時間をオフにします。 監視、ベースラインの設定、環境の一般的なはこの値を適切に設定を判断するだけの正確な方法です。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>外部自動検出 SAN および URL の既存の Web 公開ルールを変更する

1. リバース プロキシのインターフェイスを開きます。
    
2. Web 公開ルールを見つけ、(メニューまたは、リバース プロキシの構成] タブをできない場合があります) の編集] オプションを選択する必要があります。
    
3. 領域は、この web 公開ルールの適用することを示す必要があります。 着信サイトやサイトへのリクエストに関するこのルールを変更する必要があります。 新しいエントリーを**追加**します。
    
4. (使用例では lyncdiscover.contoso.com)、自動検出サイトの名前を入力し、リバース プロキシの形式に応じて、[ **OK** ] または [**保存**するには、します。
    
5. 自動検出 SAN エントリーのある新しい証明書が付与されている場合があります。 インストールして、リバース プロキシの設定によって使用できるように構成する必要があります。 構成が完了したら、必ずすべてを保存してください。
    
6. **テスト**機能、リバース プロキシの場合は、クリックしてくださいすべてことを確認するのには、それを使用して正常に動作します。
    
7. ディレクターまたはディレクターがある場合、同じ手順をする必要がありますようになりましたが、環境内のプール (つまり、2 番目のルールがある場合)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>自動検出 URL を外部の web 公開ルールを作成します。

1. リバース プロキシのインターフェイスを開きます。
    
2. 場所インターフェイスで、web 公開ルールを作成して (ある可能性がありますメニューの [または] タブで、リバース プロキシの構成によって)、または [**新規****作成**] オプションを選択するを検索する必要があります。 新しい Web 公開ルールを作成するためのオプションを探します。
    
3. 一般的に次の情報を入力する必要があります。
    
   - **名前**: 規則の名前
    
   - **ルールの処理**:**許可**ルールはここでは、できるようにする、リバース プロキシを通過するものです。
    
   - 選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。
    
   - 外部アクセス用に **SSL** にする必要があるため、そのオプションを選択します。
    
   - **内部発行**のパスを発行し、フロント エンド プールのロード バランサー (またはいずれかの操作をした場合に、ディレクター プールのロード バランサーの FQDN) を外部の Web サービスの FQDN を入力する必要があります。 しようとしている、例として sfb_ があります。pool01.contoso.local。
    
   - 入力する必要があります**/***、公開へのパスですが、**元のホスト ヘッダーを転送**する必要もします。
    
   - **パブリック名または外部名**の詳細や情報のオプションがあります。ここに
    
   - **Accept requests** と入力できますが、これはドメイン名用です。
    
   - **名前**には **lyncdiscover.** <sipdomain>これは、外部の自動検出サービスの URL)。 ここで、フロント エンド プールの外部 Web サービスの URL のルールを作成する場合は、フロント エンド プール (たとえば、lyncwebextpool01.contoso.com) では、外部の Web サービスの FQDN を入力する必要があります。
    
   - [**パス**] オプションがあり、入力する必要があります**/*** ここでは。
    
   - 最新のユーザー アカウントで **SSL リスナー**を選択する必要があります。
    
   - **認証の委任**を [**委任できません。** クライアントの直接認証を**** 許可します] に設定します。
    
   - ルールが**全ユーザー**に設定されます。
    
   - これがこのルールを作成して、手順を進めるために必要なすべての情報です。
    
4. **元のホスト ヘッダー**が転送されたか確認する必要があります。
    
5. **Web サーバー**のポートも設定する必要があります。次のように設定します。
    
   - 
            [**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号を  **8080** にします。
    
   - 
            [**SSL ポートに要求をリダイレクトする**] を選択し、ポート番号を  **4443** にします。
    
6. すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>ポート 80 の Web 公開ルールを作成する (オプション)

1. リバース プロキシのインターフェイスを開きます。
    
2. 場所インターフェイスで、web 公開ルールを作成して (ある可能性がありますメニューの [または] タブで、リバース プロキシの構成によって)、または [**新規****作成**] オプションを選択するを検索する必要があります。 新しい Web 公開ルールを作成するためのオプションを探します。
    
3. 一般的に次の情報を入力する必要があります。
    
   - **名前**: 規則の名前
    
   - **ルールの処理**:**許可**ルールはここでは、できるようにする、リバース プロキシを通過するものです。
    
   - 選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。
    
   - これは [**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] にする必要があります。
    
   - **内部発行**のパスを発行し、フロント エンド プールのロード バランサーの**VIP アドレス**の FQDN を入力する必要がありますしようとしている、例として sfb_pool01.contoso.local があります。
    
   - 入力する必要があります**/***、公開へのパスですが、**元のホスト ヘッダーを転送**する必要もします。
    
   - **パブリック名または外部名**の詳細や情報のオプションがあります。ここに
    
   - **Accept requests** と入力できますが、これはドメイン名用です。
    
   - **名前**には **lyncdiscover.** <sipdomain>これは、外部の自動検出サービスの URL)。
    
   - [**パス**] オプションがあり、入力する必要があります**/*** ここでは。
    
   - Web リスナーを選択するか、リバース プロキシを作成するを許可する必要があります。
    
   - **認証の委任**を [**委任できません。** クライアントの直接認証を**** 許可します] に設定します。
    
   - ルールが**全ユーザー**に設定されます。
    
   - これがこのルールを作成して、手順を進めるために必要なすべての情報です。
    
4. **Web サーバー**のポートを設定する必要があります。次のように設定します。
    
   - 
            [**HTTP ポートに要求をリダイレクトする**] を選択し、ポート番号を  **8080** にします。
    
   - 
            [**SSL ポートに要求をリダイレクトする**] を選択し、ポート番号を  **4443** にします。
    
5. すべての構成が終了したら、構成内容を保存または適用してからルールをテストできます。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>ハイブリッド展開でのモビリティの自動検出を構成する
<a name="ConfigAutoD"> </a>

Skype ビジネス サーバー用のハイブリッド環境は、設置を組み合わせた環境および O365 環境です。 ハイブリッド環境で作業しているビジネス サーバーの Skype すると、自動検出サービスをユーザーがこれらの環境のいずれかの方法を見つけることができる必要があります。
  
モバイル クライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい URL で構成する必要があります。手順は次のとおりです。
  
1. Skype をビジネス サーバー管理シェルを開きます。
    
2. ビジネス サーバー環境に、Skype の**ProxyFQDN**属性の値を取得するのには、次を実行します。
    
   ```
   Get-CsHostingProvider
   ```

3. それからシェル ウィンドウ内で以下を実行します。
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    [identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。
    
## <a name="test-your-mobility-deployment"></a>モビリティ展開をテストする
<a name="TestMobility"> </a>

ビジネス サーバーの自動検出サービスのビジネス サーバー移動のサービスは、Skype の Skype を展開して、確認作業の配置の右に、テスト トランザクションを実行します。 **Test-CsUcwaConference** を実行して、会議における 2 人のユーザーの作成、参加、および通信能力をテストできます。 ユーザー (実際のユーザーまたはテスト ユーザー) 2人とテストを行うための完全な資格情報が必要になります。 Lync Server 2013 クライアントだけでなく、ビジネス クライアントの両方 Skype のこのコマンドが動作します。
  
ビジネス サーバー 2015 の Skype の Lync Server 2010 クライアントは、テストに**テスト CsMcxP2PIM**を実行する必要があります。 Lync Server 2010 ユーザーがする必要が実際のユーザーまたはユーザーの定義済みのテスト、およびパスワード資格情報を必要があります。

> [!NOTE]
> 従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。 ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。 MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Skype for Business and Lync 2013 モバイル クライアントのテスト会議

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされている任意のコンピューター上の**CsAdministrator**ロールのメンバーとしてログオンします。
    
2. **ビジネス サーバー管理シェルの Skype** (可能性があります検索に名前を入力または**すべてのプログラム**に移動して選択) を起動します。
    
3. コマンドラインで、次のように入力します。
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 モバイル クライアントのテスト会議

> [!NOTE]
> 従来のモバイル クライアント用の MCX (移動サービス) サポートがビジネス サーバー 2019 の Skype で利用可能ではありません。 ビジネスのモバイル クライアントのすべての現在 Skype は、インスタント メッセージング (IM)、プレゼンス、および取引先担当者をサポートするために既にユニファイド コミュニケーション Web API (UCWA) を使用します。 MCX を使用する従来のクライアントを持つユーザーは、現在のクライアントにアップグレードする必要があります。

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされている任意のコンピューター上の**CsAdministrator**ロールのメンバーとしてログオンします。
    
2. **ビジネス サーバー管理シェルの Skype** (可能性があります検索に名前を入力または**すべてのプログラム**に移動して選択) を起動します。
    
3. コマンドラインで、次のように入力します。
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

コマンド プロシージャについて詳細を調べるには、「[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)」および「 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)」を参照してください。
  
## <a name="configure-for-push-notifications"></a>プッシュ通知を構成する
<a name="ConfigPush"> </a>

プッシュ通知は、Skype または Lync アプリが非アクティブであっても、バッジ、アイコン、または警告の形式で送信できます。 ところでプッシュ通知とはどのようなものでしょうか。 これはユーザーに、新規または不在着信の IM 招待状、受信したボイス メールなどのイベントを通知するものです。 業務でサーバーの移動サービスの Skype は、ビジネス サーバー プッシュ通知サービスは、送信通知マイクロソフト プッシュ通知サービス (MSN) に Windows Phone ユーザーのクラウド ベースの Skype にこれらの通知を送信します。
  
この機能は、Lync Server 2013 から変更されたが、ビジネス サーバーは、Skype があれば、以下を実行するでしょう。
  
- ビジネス エッジ サーバーの Skype では、新しいホスティング プロバイダーのビジネス オンラインでは、Microsoft の Skype を追加し、設定し、オンライン ビジネスの組織と Skype のプロバイダーのフェデレーションをホストしています。
    
- プッシュ通知を有効にするには、 **Set-CsPushNotificationConfiguration** コマンドレットを実行する必要があります。既定では、プッシュ通知は無効になっています。
    
- フェデレーション構成とプッシュ通知をテストする
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Skype for Business エッジ サーバーのプッシュ通知を構成する

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。
    
2. **Skype ビジネス サーバー管理シェル**を起動します。
    
3. ビジネス サーバー オンラインのホスティング プロバイダーに、Skype を追加します。
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例:
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 単一のホスティング プロバイダーに対して複数のフェデレーション関係を持つことはできません。そのため sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既に設定している場合は、ホスティング プロバイダーの ID が SkypeOnline 以外のものであっても、別のホスティング プロバイダーを追加しないでください。 
  
4. ホスティング プロバイダー フェデレーションの組織と Skype でプッシュ通知サービスとの間のオンライン ビジネスを設定します。 コマンド ラインで次ぎように入力します。
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>プッシュ通知を有効にする

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。
    
2. **Skype ビジネス サーバー管理シェル**を起動します。
    
3. プッシュ通知を有効にする:
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. フェデレーションを有効にする:
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>フェデレーションとプッシュ通知をテストする

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。
    
2. **Skype ビジネス サーバー管理シェル**を起動します。
    
3. フェデレーションの構成をテストする
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    例:
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. プッシュ通知をテストする
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    例:
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>モビリティ ポリシーを構成する
<a name="ConfigMob"> </a>

機能がある場合、モバイル サービスを使用できるユーザーを決定するビジネス サーバーの Skype でを使用して通話作業、ボイス オーバー IP (VoIP)、またはビデオ、WiFi が VoIP またはビデオのために必要になるかどうかも。 [勤務先から通話] 機能では、モバイル ユーザーが携帯電話の番号ではなく、勤務先の電話番号を使用して携帯電話で通話を発信および着信できます。 この機能により、相手に発信者の携帯電話番号が表示されるのを防ぎ、発信の電話料金を回避できます。 VoIP およびビデオを設定すると、VoIP 通話の発信と着信やビデオの利用ができるようになります。 また、WiFi の使用法の設定では、携帯電話会社の回線経由での WiFi ネットワークの使用をユーザーのデバイスで必須にするかどうかを決められます。
  
移動作業を使用して呼び出し、VoIP、ビデオ機能は、すべて既定で有効にします。 VoIP およびビデオで WiFi を必須にする設定は無効になっています。 管理者は、グローバルに、サイト別に、またはユーザー別にこれらの機能を変更できます。
  
モビリティ機能や呼び出しを使用することができるユーザーは、作業を使用する必要があります。
  
- Skype のビジネス サーバー対応
    
- エンタープライズ VoIP が有効。
    
- **EnableMobility**オプションが**True**に設定されているモビリティ ポリシーが割り当てられます。
    
[勤務先から通話] を使用するには、ユーザーが次の前提条件も満たしている必要があります。
  
- [**電話の同時呼び出しを有効にする **] オプションを選択した音声ポリシーが割り当てられている。
    
- **True**に設定する**EnableOutsideVoice**を持つモビリティ ポリシーが割り当てられます。
    
> [!NOTE]
> エンタープライズ VoIP が有効になっていないユーザーは、関連付けられている音声ポリシーのオプション設定が適切であれば、モバイル デバイスで [クリックして参加] リンクを使用すれば、モバイル デバイスから Skype 間の VoIP 通話や会議参加会議ができます。 
  
### <a name="modify-global-mobility-policy"></a>グローバル モビリティ ポリシーを変更する

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。
    
2. **Skype ビジネス サーバー管理シェル**を起動します。
    
3. オフに移動し、作業を使用して呼び出しへのアクセスをグローバルに入力しています。
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > モビリティへのアクセスを無効にすることがなく作業を使用して呼び出しを無効にできます。 することはできませんを無効に移動も作業を使用して呼び出しを無効にします。 
  
    詳細については、[一連の CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)をご覧ください。
    
### <a name="modify-mobility-policy-by-site"></a>サイトでのモビリティ ポリシーを変更します。

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。
    
2. **Skype ビジネス サーバー管理シェル**を起動します。
    
3. サイト レベルのポリシーを作成し、VoIP とビデオを無効にして、IP オーディオと IP ビデオに対して WiFi を必須にする機能をサイト別に有効にします。次のように入力します。
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    詳細については、「 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)」を参照してください。
    
### <a name="modify-mobility-policy-by-user"></a>ユーザーがモビリティ ポリシーを変更します。

1. **ビジネス サーバー管理シェルの Skype**と**Ocscore**がインストールされているコンピューターに、 **CsAdministrator**ロールのメンバーであるアカウントを使用して、ログインします。
    
2. **Skype ビジネス サーバー管理シェル**を起動します。
    
3. モビリティ ・ レベル ・ ポリシーにユーザーを作成し、モビリティ、および呼び出しを無効にユーザーの作業を使用しています。 次のように入力します。
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    サンプル データ付き詳細例:
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > モビリティへのアクセスを無効にすることがなく作業を使用して呼び出しを無効にできます。 することはできませんを無効に移動も作業を使用して呼び出しを無効にします。 
  

