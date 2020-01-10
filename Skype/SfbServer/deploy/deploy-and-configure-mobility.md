---
title: Skype for Business Server のモビリティの展開と構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この記事では、モバイルデバイスで Skype for business Server のモバイル機能を利用できるように、既存の Skype for Business Server のインストールを設定する手順について説明します。
ms.openlocfilehash: 3e39c354fd77d7ac36e3a4c36ed7e36e1d8ffbbf
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002867"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Skype for Business Server のモビリティの展開と構成  
 
この記事では、モバイルデバイスで Skype for business Server のモバイル機能を利用できるように、既存の Skype for Business Server のインストールを設定する手順について説明します。
  
[Skype For Business server のモバイルプランの計画](../plan-your-deployment/mobility.md)を確認した後、次の手順に従って Skype For business server 環境にモビリティを展開する準備ができている必要があります。 手順は次のとおりです (この表には許可一覧も含めます)。
  
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
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="create-dns-records"></a>DNS レコードの作成
<a name="CreateDNSRec"> </a>

すでに Skype for Business Server 環境に含まれている場合もありますが、自動検出機能を使用するには、次のレコードを作成する必要があります。
  
- 組織のネットワーク内から接続するモバイル ユーザーをサポートするための内部 DNS レコード。
    
- 組織のネットワーク外から接続するモバイル ユーザーをサポートするための外部 (またはパブリック) DNS レコード。
    
これらのレコードは、A (ホスト) 名または CNAME のどちらかにできます (両方作成する必要はなく、すべての手順がここに含まれています)。
  
### <a name="create-an-internal-dns-cname-record"></a>内部 DNS CNAME レコードを作成する

1. **Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。
    
2. [**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。
    
3. コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームになっているドメインに移動して、そこにある [**前方参照**] を展開する必要があります。
    
4. 次のどちらがあるか確認します。
    
   - いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。
    
   - ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。
    
5. 判別できたら SIP ドメイン名を右クリックしてから、[**新しいエイリアス (CNAME)**] をメニューから選択します。
    
6. [**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。
    
7. **完全修飾ドメイン名 (ターゲットホスト用の fqdn**) で、上記の手順4で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) 用の内部 WEB サービス fqdn を入力または参照する必要があります。 入力したら、[OK] をクリックします。
    
8. Skype for Business Server 環境でサポートされている各 SIP ドメイン用の、前方参照ゾーンに新しい自動検出 CNAME レコードを作成する必要があります。
    
### <a name="create-an-external-dns-cname-record"></a>外部 DNS CNAME レコードを作成する

1. ご利用のパブリック DNS プロバイダーが分かりませんので、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。
    
2. 現時点では、Skype for Business Server 用に SIP ドメインが既に存在している必要があります。 この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。
    
3. 次のどちらがあるか確認します。
    
   - いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。
    
   - ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。
    
4. その情報が得られたら、[**新しいエイリアス (CNAME)**] の作成オプションを選択することができます。
    
5. [**エイリアス名**] を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。
    
6. 次に、**ターゲットホストの fqdn**に入力する領域が必要です。上記の手順3で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) の fqdn を指定する必要があります。
    
7. Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の CNAME レコードを作成する必要がある場合は、ここで保存しておく必要があります。ただし、準備ができたら、作業内容を保存します。
    
### <a name="create-an-internal-dns-a-record"></a>内部 DNS A レコードを作成する

1. **Domain Admins** グループまたは **DnsAdmins** グループのメンバーであるネットワークの DNS サーバーにログインします。
    
2. [**スタート**] をクリックして、[**管理ツール**] を選択し (スタート メニューでオプションが選択できないときは [**検索**] が必要)、[**DNS**] をクリックして DNS 管理スナップインを開きます。
    
3. コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームになっているドメインに移動して、そこにある [**前方参照**] を展開する必要があります。
    
4. 次のどちらがあるか確認します。
    
   - いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。
    
   - ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。
    
5. 判別できたら SIP ドメイン名を右クリックしてから、[**新しいホスト (A または AAAA)**] をメニューから選択します。
    
6. [**名前**] テキストボックスに、内部自動検出サービス URL のホスト名として、「lyncdiscoverinternal」と入力します。
    
7. [ **IP アドレス**] ボックスに、上記の手順4で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) の内部 WEB サービス IP アドレスを入力します。
    
8. 入力したら [**ホストの追加**] をクリックしてから [**OK**] をクリックします。
    
9. Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 A レコードまたは AAAA レコードを作成する必要があります。 これを行うには手順 6 - 8 を必要な回数繰り返します。
    
10. 終了したら [**完了**] をクリックします。
    
### <a name="create-an-external-dns-a-record"></a>外部 DNS A レコードを作成する

1. ご利用のパブリック DNS プロバイダーがわからないため、これらの手順は汎用的なものですが、さらにお役に立てれば幸いです。新規 DNS レコードを作成可能なアカウントでパブリック DNS プロバイダーにログインしてください。
    
2. 現時点では、Skype for Business Server 用に SIP ドメインが既に存在している必要があります。 この  SIP ドメインの [**前方参照ゾーン**] を展開するか開きます。
    
3. 次のどちらがあるか確認します。
    
   - いずれかのホスト A または AAAA レコード (標準またはエンタープライズ) またはフロントエンドプール。
    
   - ディレクターまたはディレクタープールのすべての host A レコードまたは AAAA レコード (展開に含まれているオプションの構成)。
    
4. その情報が得られたら、[**新しいホスト A または AAAA**] の作成オプションを選択することができます。
    
5. **エイリアス名**を入力できるはずですので、外部自動検出サービス URL 用に「lyncdiscover」と入力する必要があります。
    
6. 次に、 **Ip Addresss**に入力する領域が必要です。これは、上記の手順3で確認した、フロントエンドプール (または単一のフロントエンドサーバー、またはディレクタープールまたはディレクター) の ip アドレスである必要があります。
    
7. ここに保存しなければならない場合があります。または、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の A レコードまたは AAAA レコードを作成する必要がある場合は、この操作を行う必要があります。準備ができたら、作業内容を保存します。
    
## <a name="modify-certificates"></a>証明書を変更する
<a name="ModCerts"> </a>

証明書の計画について質問がある場合は、「 [Skype For Business Server のモバイル機能の計画](../plan-your-deployment/mobility.md)」の記事で説明しています。 それを読んだ後で、以下の点を説明します。
  
- 新しい証明書が必要か。
    
- 認証局 (CA) に新しい証明書を申請する。
    
- PowerShell を使用して、使用中の証明書をアップグレードする。
    
- Microsoft 管理コンソール (MMC) の証明書スナップインを使用して証明書を確認します。
    
### <a name="do-i-need-new-certificates"></a>新しい証明書が必要か。

1. まず使用中の証明書の内容を確認して、必要とするエントリーの有無を調べる必要があります。 そのためには、ローカル管理者のアカウントで Skype for Business サーバーにログインする必要があります。 このアカウントには、手順中のいくつかで認証局 (CA) の発行権限も必要とされます。
    
2. Skype for Business Server 管理シェルを開きます ([スタート] メニューまたはタスクバーに固定されていない場合は、[検索] を使用して見つけることができます)。
    
3. 更新された証明書の追加を行う前に、すでに付与されている証明書の内容を知っておくことが重要となります。コマンドで次のように入力します。
    
   ```powershell
   Get-CsCertificate
   ```

4. 手順 3 で得られた情報は固有の内容です。内容を吟味して、複数のことに対して単一の証明書が付与されているのか、それとも証明書を必要とする別々のコンポーネントに別の証明書が付与されているのか判断します。**Use** パラメーターを使用すれば、証明書がどのように使われているかが分かり、**Thumbprint** パラメーターを使用すれば、証明書が同一か別々かが分かります。
    
5. 計画セクションで推奨されている SAN エントリーがあれば、申し分ありません。ない場合は、新規の証明書を 1 つ または複数の証明書を認証局に申請する必要があります (構成に依存します)。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>認証局 (CA) に新しい証明書を申請する。

1. 使用している SAN エントリを確認したら、 **1 つの証明書**(上記の手順に従って) があることを確認し、必要なエントリがすべて含まれていないことを確認しました。 新しい証明書の要求を CA に対して行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 一例として次のようになります (-Ca パラメーターを自分の認証局パスで置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. または、使用している SAN エントリが何であるかを確認した後、必要なエントリがすべて含まれていない**複数の証明書**があることがわかりました。 新しい証明書の要求を CA に対して行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 欠落した自動検出サービス SAN (-Ca パラメーターをジブの認証局パスで置き換える) を開きます。
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用するときは、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 次のような例になります (-Ca パラメーターを自分の認証局パスで置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA により新しい証明書が作成されたら、それを割り当てる必要があります。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して証明書を割り当てる

- 「新しい証明書が必要か」のセクションで判明した内容に応じて、次のうちの**いずれか 1 つ**を実行する必要があります。
    
  - すべてに対して単一の証明書しかない (どの thumbprint も同じ) 場合、これを実行します。
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 別々の証明書が付与されている (thumbprint が異なる) 場合、代わりにこれを実行します。
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Microsoft 管理コンソール (MMC)

1. MMC の証明書スナップインを使用して、証明書を調べるオプションを利用します。検索に MMC と入力すれば、アプリケーション オプションのようにポップアップします。
    
2. 証明書スナップインを追加するには、「**ファイル**] をクリックしてから [**スナップインの追加と削除...**] をクリックします (またはキーボード ショートカット **Ctrl+M** を利用してもよい)。 **証明書** が左側のウィンドウにオプションとして表示されるので、それを選択してから、ポップアップ ウィンドウで [**コンピュータ アカウント**] を選択し、[**次へ**] をクリックします。
    
3. まだポップアップ ウィンドウの中で、おそらく調べたい証明書が所属しているコンピュータ上で作業を行っているはずなので、そうであれば選択されている [**ローカル コンピュータ**] のままにします。 リモート マシンで作業を行っている場合は、ラジオ ボタンを [**別のコンピュータ**] に切り替え、そのコンピュータの QFDN を入力するか、[**参照**] ボタンを使用して AD 内でそのコンピュータを探します。 コンピューターを選択した後は、準備ができたら [**完了**] をクリックし、[ **OK]** をクリックしてスナップインを MMC に追加します。
    
4. MMC の左側のウィンドウで [**証明書**] セクションを展開します。 [**個人**] フォルダーも展開して、[**証明書**] を選択します。 これでこのストアにある証明書を見ることができます。
    
5. 表示したい証明書の場所を探すには、証明書を右クリックし、[**開く**] を選択します。
    
    > [!NOTE]
    > これはどのような証明書を知っていますか? 1つの証明書がファームのすべてに割り当てられているか、既定の Web サービスなどのさまざまな証明書がある場合は、複数の証明書を確認する必要があります。 複数の証明書の拇印は同じになります。 
  
6. **証明書** ビューが表示されたら、[**詳細**] を選択します。そこで [**サブジェクト**] を選択すると、証明書のサブジェクト名が表示され、付与されたサブジェクト名と関連プロパティが表示されます。
    
7. **サブジェクトの別名**エントリーも確認する必要があります。次のうちの 1 つまたは複数が見つかります。
    
   - このプールのプール名、または1つのサーバー名 (プールではない場合)。
    
   - 証明書が割り当てられるサーバーの名前
    
   - 簡単な URL レコード。通常、会議 (meet) とダイヤルイン (dialin)
    
   - Web サービスの内部および Web サービス外部名 (webpool01.contoso.net、webpool01.contoso.com など) は、トポロジビルダーでの選択肢と、[Web サービスの変更] オプションに基づいています。
    
   - 既に割り当てられている場合は、lyncdiscover です。\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコード。
    
     割り当てられている証明書が 2つ以上の場合は、それらを確認する必要があります (上記の注記を参照)。
    
8. Lyncdiscover を見つけた場合は、\<sipdomain\>と lyncdiscoverinternal。\<sipdomain\>レコードは、既に設定されています。 MMC を終了します。
    
9. これらが割り当てられていない場合は、新しい証明書を申請するか (上記で概説)、これらをポストリクエストでインストールする必要があります (次の PowerShell を推奨)。
    
## <a name="configure-the-reverse-proxy"></a>リバース プロキシを構成する
<a name="ConfigRP"> </a>

次の手順は、そのとおりに実行するように意図されたものではありません。と言うのは、製品の前のバージョンで、たとえば Threat Management Gateway (TMG) の構成について順を追って手順を説明しました。これを使用していないのであれば、自分のバージョンではそこから仕上げる必要があります。
  
TMG は、Microsoft によって製品として提供されていないため、まだ構成が必要な場合は、「 [Lync Server 2013 の手順](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)」を参照してください。 ただし、次の情報は、各リバースプロキシ用の特定のチュートリアル手順を提供する方法がない場合でも、より一般的に役に立ちます。
  
検討すべき重要な事柄が 2 つあります。
  
- 最初の自動検出申請を HTTPS で行いますか (それを推奨しています)。
    
  - Web 公開ルールがある場合、それを変更する必要がありますか。
    
  - まだ Web 公開ルールがないのであれば、それを作成する必要があります。
    
- 最初の自動検出申請を HTTPS で行うのであれば、規則の作成や変更も必要となります。
    
> [!NOTE]
> **重要**プロキシのタイムアウト値は、展開から展開までのさまざまな数値です。 クライアントに最適なエクスペリエンスを実現するには、展開を監視して、値を変更する必要があります。 この値は、200に設定することができます。 環境で Lync モバイルクライアントをサポートしている場合は、値を960に設定して、タイムアウト値が900である Office 365 からプッシュ通知のタイムアウトを許可する必要があります。 この値が低すぎる場合はクライアントの切断を回避するためにタイムアウト値を増やす必要があります。または、クライアントの接続が切断された後に、プロキシ経由の接続が切断されない場合は、その数を少なくする必要があります。 環境に応じた通常の監視とベースラインの設定は、この値の適切な設定を判断する唯一の唯一の方法です。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>外部自動検出 SAN および URL の既存の Web 公開ルールを変更する

1. リバースプロキシインターフェイスを開きます。
    
2. Web 公開ルールを見つけて、[編集] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブにある場合があります)。
    
3. この web 公開ルールが適用される場所を示す領域が必要です。 着信サイトやサイトへのリクエストに関するこのルールを変更する必要があります。 新しいエントリーを**追加**します。
    
4. [自動検出サイト] の名前 (使用する例は lyncdiscover.contoso.com) を入力し、リバースプロキシの形式に応じて [ **OK]** または [**保存**] をクリックします。
    
5. 自動検出 SAN エントリーのある新しい証明書が付与されている場合があります。 これは、リバースプロキシの設定に従ってインストールし、使用できるように構成する必要があります。 構成が完了したら、必ずすべてを保存してください。
    
6. リバースプロキシに**テスト**機能がある場合は、その機能を利用して、すべてが正しく動作することを確認してください。
    
7. これで、使用している環境にディレクターまたはディレクタープールがある場合は、次の手順を繰り返すことが必要になることがあります (これは、2つ目のルールがあることを意味します)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>外部の自動検出 URL 用の web 公開ルールを作成する

1. リバースプロキシインターフェイスを開きます。
    
2. Web 公開ルールを作成するインターフェイス内の場所を特定し、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブに表示される場合があります)。 新しい Web 公開ルールを作成するためのオプションを探します。
    
3. 一般的に次の情報を入力する必要があります。
    
   - **名前**: 規則の名前
    
   - **ルールアクション**: この例では、**許可**ルールであり、逆プロキシを通じて何らかの操作を行うことができます。
    
   - 選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。
    
   - 外部アクセス用に **SSL** にする必要があるため、そのオプションを選択します。
    
   - **内部公開**用のパスを公開し、フロントエンドプールのロードバランサーに外部 Web サービスの fqdn を入力する必要があります。または、所有している場合は、ディレクタープールのロードバランサーの fqdn (存在する場合は、ディレクタープールのロードバランサーの fqdn) を sfb_pool01 使用します。
    
   - 公開するパス** /** として「*」と入力しますが、**元のホストヘッダーも転送**する必要があります。
    
   - **パブリック名または外部名**の詳細や情報のオプションがあります。ここに
    
   - **Accept requests** と入力できますが、これはドメイン名用です。
    
   - **名前**には **lyncdiscover.** <sipdomain>(外部自動検出サービス URL)。 ここで、フロントエンドプールで外部 Web サービスの URL のルールを作成する場合は、外部 Web サービスの FQDN を、フロントエンドプールに入力する必要があります (たとえば、lyncwebextpool01.contoso.com)。
    
   - [ **Path** ] オプションが表示されます。ここに「 ** / ***」と入力する必要があります。
    
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

1. リバースプロキシインターフェイスを開きます。
    
2. Web 公開ルールを作成するインターフェイス内の場所を特定し、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブに表示される場合があります)。 新しい Web 公開ルールを作成するためのオプションを探します。
    
3. 一般的に次の情報を入力する必要があります。
    
   - **名前**: 規則の名前
    
   - **ルールアクション**: この例では、**許可**ルールであり、逆プロキシを通じて何らかの操作を行うことができます。
    
   - 選択する**公開**ルールやオプションは、**単一 Web サイトまたはロード バランサー**になります。
    
   - これは [**公開された Web サーバーまたはサーバー ファームへの接続に、セキュリティで保護されていない接続を使用する**] にする必要があります。
    
   - **内部公開**用のパスを公開し、フロントエンドプールのロードバランサーの**VIP アドレス**の FQDN を入力する必要がある場合は、sfb_pool01 例として「.local」と入力します。
    
   - 公開するパス** /** として「*」と入力しますが、**元のホストヘッダーも転送**する必要があります。
    
   - **パブリック名または外部名**の詳細や情報のオプションがあります。ここに
    
   - **Accept requests** と入力できますが、これはドメイン名用です。
    
   - **名前**には **lyncdiscover.** <sipdomain>(外部自動検出サービス URL)。
    
   - [ **Path** ] オプションが表示されます。ここに「 ** / ***」と入力する必要があります。
    
   - Web リスナーを選ぶか、リバースプロキシで作成する必要があります。
    
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

Skype for Business Server のハイブリッド環境は、オンプレミスと O365 の環境を組み合わせた環境です。 ハイブリッド環境で Skype for Business Server を使用している場合、自動検出サービスでは、これらの環境のいずれかからユーザーを検索できるようにする必要があります。
  
モバイル クライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい URL で構成する必要があります。手順は次のとおりです。
  
1. Skype for Business Server 管理シェルを開きます。
    
2. Skype for Business Server 環境の属性**Proxyfqdn**の値を取得するには、次を実行します。
    
   ```powershell
   Get-CsHostingProvider
   ```

3. それからシェル ウィンドウ内で以下を実行します。
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    [identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。
    
## <a name="test-your-mobility-deployment"></a>モビリティ展開をテストする
<a name="TestMobility"> </a>

Skype for Business Server Mobility Service と Skype for Business Server 自動検出サービスを展開したら、テストトランザクションを実行して、展開が正常に動作していることを確認します。 **Test-CsUcwaConference** を実行して、会議における 2 人のユーザーの作成、参加、および通信能力をテストできます。 ユーザー (実際のユーザーまたはテスト ユーザー) 2人とテストを行うための完全な資格情報が必要になります。 このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方に対応しています。
  
Skype for Business Server 2015 上の Lync Server 2010 クライアントの場合、テストのために**CsMcxP2PIM**を実行する必要があります。 Lync Server 2010 ユーザーは、実際のユーザー、または事前定義されたテストユーザーである必要があります。また、パスワード資格情報を入力する必要があります。

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Skype for Business and Lync 2013 モバイル クライアントのテスト会議

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターで、 **csadministrator**ロールのメンバーとしてログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します ([検索] に名前を入力するか、[**すべてのプログラム**] に移動して選択します)。
    
3. コマンドラインで、次のように入力します。
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 モバイル クライアントのテスト会議

> [!NOTE]
> Skype for Business Server 2019 では、従来のモバイルクライアントに対する MCX (モバイルサービス) のサポートは利用できなくなりました。 現在のすべての Skype for Business のモバイルクライアントでは、インスタントメッセージング (IM)、プレゼンス、連絡先をサポートするために、既にユニファイドコミュニケーション Web API (UCWA) を使用しています。 MCX を使用するレガシクライアントを使っているユーザーは、現在のクライアントにアップグレードする必要があります。

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターで、 **csadministrator**ロールのメンバーとしてログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します ([検索] に名前を入力するか、[**すべてのプログラム**] に移動して選択します)。
    
3. コマンドラインで、次のように入力します。
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   スクリプトに資格情報を設定して、テスト コマンドレットに渡すこともできます。下の例をご覧ください。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

コマンド プロシージャについて詳細を調べるには、「[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)」および「 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)」を参照してください。
  
## <a name="configure-for-push-notifications"></a>プッシュ通知を構成する
<a name="ConfigPush"> </a>

プッシュ通知は、Skype または Lync アプリが非アクティブであっても、バッジ、アイコン、または警告の形式で送信できます。 プッシュ通知とは何ですか? これはユーザーに、新規または不在着信の IM 招待状、受信したボイス メールなどのイベントを通知するものです。 Skype for Business Server Mobility service は、これらの通知をクラウドベースの Skype for Business Server プッシュ通知サービスに送信します。これにより、Windows Phone ユーザー用の Microsoft プッシュ通知サービス (MSNS) に通知が送信されます。
  
この機能は Lync Server 2013 から変更されませんが、Skype for Business Server をお持ちの場合は、次の操作を実行します。
  
- Skype for Business Server Edge Server の場合は、新しいホスティングプロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online の間でホスティングプロバイダーフェデレーションをセットアップします。
    
- プッシュ通知を有効にするには、 **Set-CsPushNotificationConfiguration** コマンドレットを実行する必要があります。既定では、プッシュ通知は無効になっています。
    
- フェデレーション構成とプッシュ通知をテストする
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Skype for Business エッジ サーバーのプッシュ通知を構成する

1. **Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. Skype for Business Server online ホスティングプロバイダーを追加します。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   例:
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 単一のホスティング プロバイダーに対して複数のフェデレーション関係を持つことはできません。そのため sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既に設定している場合は、ホスティング プロバイダーの ID が SkypeOnline 以外のものであっても、別のホスティング プロバイダーを追加しないでください。 
  
4. 組織と Skype for Business Online のプッシュ通知サービスとの間のホスティングプロバイダーフェデレーションをセットアップします。 コマンド ラインで次ぎように入力します。
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>プッシュ通知を有効にする

1. **Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. プッシュ通知を有効にする:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. フェデレーションを有効にする:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>フェデレーションとプッシュ通知をテストする

1. **Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. フェデレーションの構成をテストする
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    例:
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. プッシュ通知をテストする
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    例:
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>モビリティ ポリシーを構成する
<a name="ConfigMob"> </a>

Skype for Business Server を使用すると、モビリティサービスを使うことができるユーザー、勤務先の電話での通話、ボイスオーバー IP (VoIP)、ビデオのほか、VoIP またはビデオに WiFi が必要かどうかを特定することもできます。 [勤務先から通話] 機能では、モバイル ユーザーが携帯電話の番号ではなく、勤務先の電話番号を使用して携帯電話で通話を発信および着信できます。 この機能により、相手に発信者の携帯電話番号が表示されるのを防ぎ、発信の電話料金を回避できます。 VoIP およびビデオを設定すると、VoIP 通話の発信と着信やビデオの利用ができるようになります。 また、WiFi の使用法の設定では、携帯電話会社の回線経由での WiFi ネットワークの使用をユーザーのデバイスで必須にするかどうかを決められます。
  
モバイル機能、勤務先からの通話、VoIP およびビデオ機能は、すべて既定で有効になっています。 VoIP およびビデオで WiFi を必須にする設定は無効になっています。 管理者は、グローバルに、サイト別に、またはユーザー別にこれらの機能を変更できます。
  
モバイル機能を使用し、勤務先から通話を発信できるようにするには、次のことが必要です。
  
- Skype for Business Server に対応
    
- エンタープライズ VoIP が有効。
    
- **EnableMobility**オプションが**True**に設定されたモビリティポリシーが割り当てられている。
    
[勤務先から通話] を使用するには、ユーザーが次の前提条件も満たしている必要があります。
  
- [**電話の同時呼び出しを有効にする **] オプションを選択した音声ポリシーが割り当てられている。
    
- **EnableOutsideVoice**が**True**に設定されたモビリティポリシーを割り当てました。
    
> [!NOTE]
> エンタープライズ VoIP が有効になっていないユーザーは、関連付けられている音声ポリシーのオプション設定が適切であれば、モバイル デバイスで [クリックして参加] リンクを使用すれば、モバイル デバイスから Skype 間の VoIP 通話や会議参加会議ができます。 
  
### <a name="modify-global-mobility-policy"></a>グローバル モビリティ ポリシーを変更する

1. **Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. 次のように入力することにより、機動性へのアクセスをオフにして、世界中で通話を発信します
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > 「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。 ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。 
  
    詳しくは、「 [Set-set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)」をご覧ください。
    
### <a name="modify-mobility-policy-by-site"></a>サイトごとのモバイル機能ポリシーの変更

1. **Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. サイト レベルのポリシーを作成し、VoIP とビデオを無効にして、IP オーディオと IP ビデオに対して WiFi を必須にする機能をサイト別に有効にします。次のように入力します。
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    詳細については、「 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)」を参照してください。
    
### <a name="modify-mobility-policy-by-user"></a>ユーザーによるモビリティポリシーの変更

1. **Csadministrator**ロールのメンバーであるアカウントを使って、 **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターにログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. ユーザーレベルのモバイル処理ポリシーを作成し、機動性をオフにして、ユーザーによる勤務先から通話を発信します。 次のように入力します。
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    サンプル データ付き詳細例:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > 「モビリティーへのアクセスをオフにする」をオフにすると、勤務先から通話をオフにすることができます。 ただし、勤務先からの通話をオフにすることなく、モバイル機能をオフにすることはできません。 
  

