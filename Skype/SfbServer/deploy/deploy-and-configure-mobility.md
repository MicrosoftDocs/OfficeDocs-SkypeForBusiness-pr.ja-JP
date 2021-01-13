---
title: Skype for Business Server のモビリティの展開と構成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この記事では、モバイル デバイスで Skype for Business Server のモビリティ機能を利用できるように、Mobility Service を使用するために既存の Skype for Business Server インストールを構成する手順について説明します。
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820897"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Skype for Business Server のモビリティの展開と構成  
 
この記事では、モバイル デバイスで Skype for Business Server のモビリティ機能を利用できるように、Mobility Service を使用するために既存の Skype for Business Server インストールを構成する手順について説明します。
  
[「Plan for Mobility for Skype for Business Server」](../plan-your-deployment/mobility.md)の記事を確認した後、以下の手順に進み、Skype for Business Server 環境に Mobility を展開する準備が整っている必要があります。 手順は次のとおりです (この表にアクセス許可の一覧を含めます)。
  
|**フェーズ**|**アクセス許可**|
|:-----|:-----|
|[DNS レコードの作成](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[証明書を変更する](deploy-and-configure-mobility.md#ModCerts) <br/> |ローカル管理者  <br/> |
|[リバース プロキシを構成する](deploy-and-configure-mobility.md#ConfigRP) <br/> |ローカル管理者  <br/> |
|[ハイブリッド展開でのモビリティの自動検出の構成](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[モビリティの展開をテストする](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[プッシュ通知を構成する](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[モビリティ ポリシーを構成する](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
以下のすべてのセクションでは、「計画」トピックを読んだと仮定した手順について説明します。 わかりにくい場合は、その情報を自由に確認してください。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="create-dns-records"></a>DNS レコードの作成
<a name="CreateDNSRec"> </a>

これらは Skype for Business Server 環境の一部として既に存在する可能性がありますが、自動検出が機能するには次のレコードを作成する必要があります。
  
- 組織のネットワーク内から接続しているモバイル ユーザーをサポートする内部 DNS レコード。
    
- 組織のネットワークの外部から接続しているモバイル ユーザーをサポートするための外部 (またはパブリック) DNS レコード。
    
これらのレコードは、A (ホスト) 名または CNAME レコードのどちらかです (両方を作成する必要はありません。ここでは、すべて手順を含めただけです)。
  
### <a name="create-an-internal-dns-cname-record"></a>内部 DNS CNAME レコードを作成する

1. Domain Admins グループまたは **DnsAdmins** グループのメンバーであるネットワーク内の DNS **サーバーにログイン** します。
    
2. [**スタート]** ボタン、[管理ツールの選択]  **([** スタート] メニューのオプションではない場合は検索が必要な場合があります) をクリックし **、[DNS]** をクリックして DNS 管理スナップインを開きます。
    
3. コンソール ウィンドウの左側のウィンドウで、Skype for Business Server のフロント エンド サーバーにホームであるドメインに移動し、そこに前方参照ゾーンを展開する必要があります。
    
4. 次の中から次の情報を確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロントエンド プールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクター プールの任意のホスト A または AAAA レコード (展開内のオプション構成)。
    
5. これを確認したら、SIP ドメイン名を右クリックし、メニューから [新しいエイリアス **(CNAME)** を選択します。
    
6. [エイリアス **名]** ボックスに、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。
    
7. 完全修飾ドメイン名 (ターゲット ホストの **FQDN)** で、前の手順 4 で識別したフロントエンド プール (または単一のフロントエンド サーバー、ディレクター プールまたはディレクター) の内部 Web サービス FQDN を入力または参照する必要があります。 入力時に [OK] をクリックします。
    
8. Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンに新しい自動検出 CNAME レコードを作成する必要があります。
    
### <a name="create-an-external-dns-cname-record"></a>外部 DNS CNAME レコードを作成する

1. これらの手順は汎用的です。どのパブリック DNS プロバイダーを使用しているのかは判断できないので、引き続きお手伝いします。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。
    
2. この時点で、Skype for Business Server の SIP ドメインが既に存在している必要があります。 この SIP **ドメインの前方参照ゾーン** を展開するか、開きます。
    
3. 次の中から次の情報を確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロントエンド プールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクター プールの任意のホスト A または AAAA レコード (展開内のオプション構成)。
    
4. この情報を取得したら、新しいエイリアス **(CNAME) を作成するためのオプションを選択できます**。
    
5. これでエイリアス名を入力できます。外部自動検出サービスの URL には、ここで「lyncdiscover」と入力する必要があります。
    
6. 次に、ターゲット ホストの FQDN に入力する領域が表示されます。これは、前の手順 3 で識別したフロントエンド プール (または単一のフロントエンド サーバー、ディレクター プールまたはディレクター) の **FQDN** である必要があります。
    
7. ここで保存する必要がある場合や、Skype for Business Server 環境内の各 SIP ドメインの前方参照ゾーンに追加の CNAME レコードを作成する必要がある場合は、その操作を行う必要がありますが、準備ができたら作業を保存します。
    
### <a name="create-an-internal-dns-a-record"></a>内部 DNS A レコードを作成する

1. Domain Admins グループまたは **DnsAdmins** グループのメンバーであるネットワーク内の DNS **サーバーにログイン** します。
    
2. [**スタート]** ボタン、[管理ツールの選択]  **([** スタート] メニューのオプションではない場合は検索が必要な場合があります) をクリックし **、[DNS]** をクリックして DNS 管理スナップインを開きます。
    
3. コンソール ウィンドウの左側のウィンドウで、Skype for Business Server のフロント エンド サーバーにホームであるドメインに移動し、そこに前方参照ゾーンを展開する必要があります。
    
4. 次の中から次の情報を確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロントエンド プールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクター プールの任意のホスト A または AAAA レコード (展開内のオプション構成)。
    
5. これを確認したら、SIP ドメイン名を右クリックし、メニューから [新しいホスト (A または **AAAA)]** を選択します。
    
6. [名前 **]** ボックスに、内部自動検出サービスの URL に、ホスト名として「lyncdiscoverinternal」と入力します。
    
7. **[IP アドレス]** ボックスに、前の手順 4 で示したフロントエンド プール (または単一のフロントエンド サーバー、ディレクター プールまたはディレクター) の内部 Web サービス IP アドレスを入力します。
    
8. これが完了したら、[ホストの追加]**をクリックし****、[OK]** をクリックします。
    
9. Skype for Business Server 環境でサポートされている SIP ドメインごとに、前方参照ゾーンに新しい自動検出 A または AAAA レコードを作成する必要があります。 これを行うには、必要に応じて手順 6 から 8 を繰り返します。
    
10. 完了したら、[完了] をクリック **します**。
    
### <a name="create-an-external-dns-a-record"></a>外部 DNS A レコードを作成する

1. これらの手順は汎用的です。どのパブリック DNS プロバイダーを使用しているのかは判断できないので、引き続きお手伝いします。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。
    
2. この時点で、Skype for Business Server の SIP ドメインが既に存在している必要があります。 この SIP **ドメインの前方参照ゾーン** を展開するか、開きます。
    
3. 次の中から次の情報を確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロントエンド プールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクター プールの任意のホスト A または AAAA レコード (展開内のオプション構成)。
    
4. この情報を取得したら、新しいホスト A または AAAA を作成するための **オプションを選択できる必要があります**。
    
5. これで、名前を入力できます。外部自動検出サービスの URL には、ここで「lyncdiscover」と入力する必要があります。
    
6. **次に、IP** アドレスに入力する領域が必要です。これは、前の手順 3 で識別された、フロント エンド プール (または単一のフロントエンド サーバー、ディレクター プールまたはディレクター) の IP である必要があります。
    
7. ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンに追加の A レコードまたは AAAA レコードを作成する必要がある場合は、その操作を行う必要がありますが、準備ができたら作業を保存します。
    
## <a name="modify-certificates"></a>証明書を変更する
<a name="ModCerts"> </a>

証明書の計画に関する質問がある場合は [、Skype for Business Server](../plan-your-deployment/mobility.md) の Plan for Mobility に関する記事に記載されています。 確認したら、次の手順について説明します。
  
- 新しい証明書は必要ですか?
    
- 証明機関 (CA) に新しい証明書を要求する。
    
- PowerShell を使用して、置き換えで一時証明書を更新します。
    
- Microsoft 管理コンソール (MMC) で証明書スナップインを使用して証明書を確認します。
    
### <a name="do-i-need-new-certificates"></a>新しい証明書は必要ですか?

1. まず、どの証明書がイン Placeか、必要なエントリを持っているかどうかを確認する必要があります。 これを行うには、ローカル管理者のアカウントを使用して Skype for Business Server にログインする必要があります。 このアカウントには、発行元の証明機関 (CA) に対する権限が必要な場合があります。これらの手順のいくつかについて説明します。
    
2. Skype for Business Server 管理シェルを開きます (スタート メニューまたはタスク バーにピン留めされていない場合は、検索を使用して検索できます)。
    
3. 更新された証明書を追加する前に、どの証明書が割り当てられているかを知る必要があります。 そのため、コマンドで次のコマンドを入力します。
    
   ```powershell
   Get-CsCertificate
   ```

4. 手順 3 の情報は、ユーザーに固有の情報です。 複数の要素に割り当てられている証明書が 1 つかどうか、またはそれらを必要とする異なるコンポーネントに異なる証明書が割り当てられているかどうかを判断するには、この情報を確認する必要があります。 **Use パラメーター** は証明書の使用方法を示し **、Thumbprint** パラメーターは証明書が同じ証明書か複数の証明書かを示します。
    
5. 「計画」セクションで推奨されている SAN エントリがある場合は、問題ない場合があります。 要求されていない場合は、新しい証明書、または構成に応じて複数の証明書を証明機関に要求する必要があります。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>証明機関 (CA) に新しい証明書または証明書を要求する

1. 自分が持っている SAN エントリを確認した後、(上記の手順を確認した後で) 1 つの証明書を持っているのが分かっています。また、必要なエントリが一部ないという学習を行いました。 CA に新しい証明書要求を行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 不足している自動検出サービス SAN の場合 (-Ca パラメーターを独自の証明機関パスに置き換える):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 複数の SIP ドメインがある場合、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。 たとえば、次のようになります (-Ca パラメーターを独自の証明機関パスに置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. または、使用している SAN エントリを確認した後、必要なエントリの一部を持っていない複数の証明書が見つかりました。 CA に新しい証明書要求を行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 不足している自動検出サービス SAN の場合 (-Ca パラメーターを独自の証明機関パスに置き換える):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 複数の SIP ドメインがある場合、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。 たとえば、次のようになります (-Ca パラメーターを独自の証明機関パスに置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA によって新しい証明書が生成された後、それらを割り当てる必要があります。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して証明書を割り当てる

- 上記の「新しい認定が必要か」セクションで確認した内容に応じて、次のいずれかを実行 **する** 必要があります。
    
  - すべての証明書に 1 つの証明書がある場合 (拇印は同じです)、次のコマンドを実行する必要があります。
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 証明書の種類が異なる場合 (拇印はすべて異なります)、代わりに次のコマンドを実行します。
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Microsoft 管理コンソール (MMC) での証明書の表示

1. MMC の証明書スナップインを使用して証明書を確認するオプションがあります。 検索に MMC と入力するだけで、アプリケーション オプションとしてポップアップ表示されます。
    
2. 証明書スナップインを追加するには、[ファイル] をクリックし、[スナップインの追加と削除] をクリックする必要があります **(または**、キーボード ショートカット Ctrl **+ M** も機能します)。 **左側の** ウィンドウで証明書を選択し、ポップアップ ウィンドウでコンピューター アカウントを選択し、[次へ] をクリック **します**。
    
3. 引き続きポップアップ ウィンドウでは、確認する必要がある証明書が存在するコンピューターでこれを行う可能性が高いので、その場合はローカル コンピューターで選択を残します。 リモート コンピューターで作業している場合は、ラジオ ボタンを別のコンピューターに変更し、そのコンピューターの FQDN を入力するか、[参照] ボタンを使用して AD を介してそのコンピューターを検索します。 コンピューターを選択したら、準備ができたら [完了]をクリックし **、[OK]** をクリックしてスナップインを MMC に追加する必要があります。
    
4. MMC **の左側** のウィンドウで [証明書] セクションを展開します。 [個人用] **フォルダー** も展開し、[証明書] **を選択します**。 これにより、このストア内の証明書を表示できます。
    
5. 表示する証明書を見つけて右クリックし、[開く] を選択する必要 **があります**。
    
    > [!NOTE]
    > これが何の証明書かを知る方法 ファームのすべてに割り当てられた単一の証明書か、Default、Internal Web Services など、さまざまなものに対して複数の証明書を持つ必要があります。その場合は、複数の証明書を確認する必要があります。 複数の証明書が同じ拇印を持つ。 
  
6. [証明書] ビューが表示された **後、[** 詳細] を選択 **します**。 これにより、[サブジェクト] を選択すると証明書のサブジェクト名が表示され、割り当てられたサブジェクト名と関連プロパティが表示されます。
    
7. サブジェクトの代替名のエントリ **も確認する** 必要があります。 次の 1 つ以上の情報が表示されます。
    
   - このプールのプール名、またはプールではない場合は単一のサーバー名。
    
   - 証明書が割り当てられているサーバー名。
    
   - 簡易 URL レコード (通常は meet と dialin)。
    
   - トポロジ ビルダーでの選択および過剰な Web サービスの選択に基づいて、Web サービス内部および Web サービスの外部名 (webpool01.contoso.net、webpool01.contoso.com など)。
    
   - 既に割り当てられている場合は、lyncdiscover。\<sipdomain\> lyncdiscoverinternal。\<sipdomain\> レコードを追加します。
    
     複数の証明書が割り当てられている場合は、複数の証明書を確認する必要があります (上記の注を確認してください)。
    
8. そのため、lyncdiscover が見つけた場合です。\<sipdomain\> lyncdiscoverinternal。\<sipdomain\> レコードが既に構成されています。 MMC を閉じできます。
    
9. 割り当てられていない場合は、新しい証明書要求 (上記の説明) を行う必要があります。または、要求後にそれらをインストールする必要があります (このためには、上記の PowerShell を次に示す方法をお勧めします)。
    
## <a name="configure-the-reverse-proxy"></a>リバース プロキシを構成する
<a name="ConfigRP"> </a>

以下の手順は、正確に従う必要があるという意味ではありません。 これは、製品の以前のバージョンでは、脅威管理ゲートウェイ (TMG) の構成などについて説明しました。使用しない場合は、そこから独自のバージョンを作成する必要があります。
  
TMG は製品として Microsoft によって提供されなくなりました。それでも構成する必要がある場合は [、Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)の手順を確認できます。 ただし、次の情報は、すべてのリバース プロキシに対して特定のチュートリアル手順を提供する方法がない場合でも、より一般的に役立ちます。
  
次の 2 つの主な点を考慮する必要があります。
  
- 最初の自動検出要求を HTTPS 経由で実行しますか (推奨)。
    
  - Web 公開ルールがある場合は、それを変更する必要があります。
    
  - Web 公開ルールがまだない場合は、作成する必要があります。
    
- 最初の自動検出要求を HTTP で実行する場合は、そのルールも作成または変更する必要があります。
    
> [!NOTE]
> **重要** プロキシのタイム アウト値は、展開によって異なる数値です。 展開を監視し、クライアントに最適なエクスペリエンスを提供するために値を変更する必要があります。 値を 200 に設定できる場合があります。 環境で Lync モバイル クライアントをサポートしている場合は、この値を 960 に設定して、Office 365 からのプッシュ通知のタイム アウトを許可する必要があります。この場合、この値は 900 というタイム アウト値になります。 値が小さすぎるときにクライアントの切断を回避するために、タイム アウト値を増やす必要がある可能性が高いです。または、プロキシ経由の接続が切断されないが、クライアントが切断された後に長くクリアする場合は、番号を減らします。 この値の適切な設定を決定するには、環境に対して通常の状態を監視および基本化する唯一の正確な方法です。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>外部自動検出 SAN と URL の既存の Web 公開ルールを変更する

1. リバース プロキシ インターフェイスを開きます。
    
2. Web 公開ルールを見つけて、[編集] オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブに表示される場合があります)。
    
3. この Web 公開ルールの適用を示す領域が必要です。 受信サイトまたはサイトの要求に対してこのルールを変更する必要があります。 新しいエントリを **追加** します。
    
4. 自動検出サイトの名前 (使用する例は lyncdiscover.contoso.com) を入力し、リバース プロキシの形式に応じて **[OK]** または [保存] をクリックします。
    
5. 自動検出 SAN エントリを持つ新しい証明書が作成されている場合があります。 これは、リバース プロキシの設定に従ってインストールし、使用するように構成する必要があります。 構成が完了したら、必ずすべてを保存してください。
    
6. リバース プロキシにテスト機能がある場合は、それを利用して、すべてが正常に動作しているのを確認してください。
    
7. 環境にディレクターまたはディレクター プールがある場合は、これらの手順を繰り返す必要がある場合があります (これは、2 番目のルールがあるという意味です)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>外部自動検出 URL の Web 公開ルールを作成する

1. リバース プロキシ インターフェイスを開きます。
    
2. Web 公開ルールを作成するインターフェイス内の場所を特定し、[新規] または [作成]オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブ上にある場合があります)。 新しい Web 公開ルールを作成するオプションを探しています。
    
3. 通常、次の情報を入力する必要があります。
    
   - **Name**: ルールの名前
    
   - **ルールの** 処理 : この場合は許可 **ルールですが、** リバース プロキシを経由して何かを渡します。
    
   - 選択 **する公開** ルールまたはオプションは、単一の Web サイトまたは **ロード バランサーです**。
    
   - これは外部アクセス用 **の SSL** である必要があります。このオプションを選択します。
    
   - 内部公開のパスを公開し、フロントエンド プールのロード バランサー上の外部 Web サービスの FQDN (ディレクター プールのロード バランサーの FQDN がある場合は FQDN) を入力する必要があります。たとえば、sfb_pool01.contoso.local のようになります。
    
   - 公開するパスとして「_」と入力する必要がありますが、元のホスト ヘッダー **/\\** を _*転送する必要があります**。
    
   - パブリックまたは外部の名前の **詳細または情報の** オプションがあります。 ここで、次の情報を入力できます。
    
   - **要求を受け** 入れるが、ドメイン名用である必要がある。
    
   - [名前 **] に****「lyncdiscover」と入力する必要があります。** <sipdomain> (これは外部自動検出サービス URL です)。 ここで、フロントエンド プールで外部 Web サービス URL のルールを作成する場合は、フロントエンド プールの外部 Web サービスの FQDN を入力する必要があります (lyncwebextpool01.contoso.com など)。
    
   - [パス] **オプション** が表示され、ここに 「_」と **/\\** 入力する必要があります。
    
   - 最新のパブリック証明書を使用して_ *SSL リスナー** を選択する必要があります。
    
   - **認証委任は** [委任なし] に **設定する必要** がありますが、直接クライアント **認証を許可** する必要があります。
    
   - ルールは、[すべてのユーザー] に **設定する必要があります**。
    
   - これは、このルールを作成するために必要なすべての情報であり、続行できる必要があります。
    
4. 元のホスト ヘッダーが転送 **されるのを確認する** 必要があります。
    
5. Web **サーバー ポート** も設定する必要があります。次の操作を行う必要があります。
    
   - **HTTP ポートへのリダイレクト要求と** ポート番号は **8080 である必要があります**。
    
   - **SSL ポートへのリダイレクト要求と** ポート番号は **4443 である必要があります**。
    
6. すべてを構成したら、これらを保存または適用する必要があります。その後、ルールをテストします。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>ポート 80 の Web 公開ルールを作成する (オプション)

1. リバース プロキシ インターフェイスを開きます。
    
2. Web 公開ルールを作成するインターフェイス内の場所を特定し、[新規] または [作成]オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブ上にある場合があります)。 新しい Web 公開ルールを作成するオプションを探しています。
    
3. 通常、次の情報を入力する必要があります。
    
   - **Name**: ルールの名前
    
   - **ルールの** 処理 : この場合は許可 **ルールですが、** リバース プロキシを経由して何かを渡します。
    
   - 選択 **する公開** ルールまたはオプションは、単一の Web サイトまたは **ロード バランサーです**。
    
   - 発行された Web サーバーまたはファームに接続するには、セキュリティで保護されていない **接続である必要があります**。
    
   - 内部公開のパスを公開し、フロントエンド プールのロード バランサーの VIP アドレスの **FQDN** を入力する必要があります。たとえば、sfb_pool01.contoso.local のようになります。
    
   - 公開するパスとして「_」と入力する必要がありますが、元のホスト ヘッダー **/\\** を _*転送する必要があります**。
    
   - パブリックまたは外部の名前の **詳細または情報の** オプションがあります。 ここで、次の情報を入力できます。
    
   - **要求を受け** 入れるが、ドメイン名用である必要がある。
    
   - [名前 **] に****「lyncdiscover」と入力する必要があります。** <sipdomain> (これは外部自動検出サービス URL です)。
    
   - [パス] **オプション** が表示され、ここに 「_」と **/\\** 入力する必要があります。
    
   - Web リスナーを選択するか、リバース プロキシで作成を許可する必要があります。
    
   - _ *認証委任** は[委任なし] に設定する必要がありますが、直接クライアント **認証は許可** されません。
    
   - ルールは、[すべてのユーザー] に **設定する必要があります**。
    
   - これは、このルールを作成するために必要なすべての情報であり、続行できる必要があります。
    
4. Web **サーバー ポート** を設定する必要があります。次の操作を行う必要があります。
    
   - **HTTP ポートへのリダイレクト要求と** ポート番号は **8080 である必要があります**。
    
   - **SSL ポートへのリダイレクト要求と** ポート番号は **4443 である必要があります**。
    
5. すべてを構成したら、これらを保存または適用する必要があります。その後、ルールをテストします。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>ハイブリッド展開でのモビリティの自動検出の構成
<a name="ConfigAutoD"> </a>

Skype for Business Server のハイブリッド環境は、オンプレミス環境と O365 環境を組み合わせた環境です。 Skype for Business Server がハイブリッド環境で動作している場合、自動検出サービスは、これらの環境のどちらかからユーザーを検索できる必要があります。
  
モバイル クライアントがユーザーの場所を検出するには、自動検出サービスを新しい URL (Uniform Resource Locator) で構成する必要があります。 手順は次のとおりです。
  
1. Skype for Business Server 管理シェルを開きます。
    
2. 次を実行して、Skype for Business Server 環境の **ProxyFQDN** 属性の値を取得します。
    
   ```powershell
   Get-CsHostingProvider
   ```

3. その後もシェル ウィンドウで、次のコマンドを実行します。
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    [identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。
    
## <a name="test-your-mobility-deployment"></a>モビリティの展開をテストする
<a name="TestMobility"> </a>

Skype for Business Server Mobility Service と Skype for Business Server 自動検出サービスを展開したら、テスト トランザクションを実行して、展開が正しく動作する必要があります。 **Test-CsUcwaConference** を実行すると、2 人のユーザーが会議を作成、参加、および通信する機能をテストできます。 このテストを実行するには、2 人のユーザー (実際またはテスト) と完全な資格情報が必要です。 このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方で機能します。
  
Skype for Business Server 2015 上の Lync Server 2010 クライアントの場合は **、Test-CsMcxP2PIM** を実行してテストする必要があります。 Lync Server 2010 ユーザーは、実際のユーザー、または定義済みのテスト ユーザーである必要があります。また、ユーザーのパスワード資格情報が必要です。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Skype for Business および Lync 2013 モバイル クライアントのテスト会議

1. **Skype for Business Server** 管理シェルと **Ocscore** がインストールされている任意のコンピューターで **、CsAdministrator** の役割のメンバーとしてログオンします。
    
2. Skype **for Business Server 管理シェルを起動** します (検索に名前を入力するか、[すべてのプログラム] に移動 **して** 選択できます)。
    
3. コマンド ラインで、次のコマンドを入力します。
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   スクリプトで資格情報を設定し、テスト コマンドレットに渡す方法も可能です。 この例を次に示します。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 モバイル クライアントのテスト会議

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。

1. **Skype for Business Server** 管理シェルと **Ocscore** がインストールされている任意のコンピューターで **、CsAdministrator** の役割のメンバーとしてログオンします。
    
2. Skype **for Business Server 管理シェルを起動** します (検索に名前を入力するか、[すべてのプログラム] に移動 **して** 選択できます)。
    
3. コマンド ラインで、次のコマンドを入力します。
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   スクリプトで資格情報を設定し、テスト コマンドレットに渡す方法も可能です。 この例を次に示します。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

コマンドの手順をさらに確認するには [、Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) と [Test-CsMcxP2PIM を確認してください](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>プッシュ通知を構成する
<a name="ConfigPush"> </a>

プッシュ通知は、Skype または Lync アプリが非アクティブな場合でも、バッジ、アイコン、またはアラートの形式でモバイル デバイスに送信できます。 しかし、プッシュ通知とは これらは、新しい IM の招待や見つからない IM の招待、受信したボイスメールに関するイベントアラートです。 Skype for Business Server Mobility サービスは、これらの通知をクラウドベースの Skype for Business Server プッシュ通知サービスに送信し、Windows Phone ユーザー向け Microsoft プッシュ通知サービス (MSNS) に通知を送信します。
  
この機能は Lync Server 2013 から変更されていませんが、Skype for Business Server を使用している場合は、次の操作を行う必要があります。
  
- Skype for Business Server エッジ サーバーの場合は、新しいホスティング プロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online 間のホスティング プロバイダー フェデレーションを設定します。
    
- **Set-CsPushNotificationConfiguration** コマンドレットを実行して、プッシュ通知を有効にします。 既定では、プッシュ通知はオフになっています。
    
- フェデレーション構成とプッシュ通知をテストします。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>プッシュ通知用に Skype for Business エッジ サーバーを構成する

1. **CsAdministrator** の役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. Skype for Business Server オンライン ホスティング プロバイダーを追加します。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   次に例を示します。
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 1 つのホスティング プロバイダーと複数のフェデレーション関係を持つ必要があります。 そのため、sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既にセットアップしている場合は、ホスティング プロバイダーの ID が SkypeOnline 以外の場合でも、別のホスティング プロバイダーを追加する必要があります。 
  
4. Skype for Business Online で、組織とプッシュ通知サービス間のホスティング プロバイダー フェデレーションを設定します。 コマンド ラインで、次のコマンドを入力する必要があります。
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>プッシュ通知を有効にする

1. **CsAdministrator** の役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. プッシュ通知を有効にします。
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. フェデレーションを有効にする:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>フェデレーションとプッシュ通知のテスト

1. **CsAdministrator** の役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. フェデレーション構成をテストします。
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    次に例を示します。
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. プッシュ通知をテストします。
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    次に例を示します。
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>モビリティ ポリシーを構成する
<a name="ConfigMob"> </a>

Skype for Business Server を使用すると、モビリティ サービス、[通話]、ボイス オーバー IP (VoIP)、ビデオを使用できるユーザー、および VoIP またはビデオに WiFi が必要かどうかを判断できます。 [仕事から通話] では、携帯電話のユーザーが通話を送受信するときに、携帯電話の番号ではなく、自分の仕事用の電話番号を使用できます。 回線のもう一方の端のユーザーには、そのモバイル ユーザーの携帯電話番号が表示されなく、そのモバイル ユーザーは発信通話料金を回避できます。 VoIP とビデオをセットアップすると、ユーザーは VoIP 通話とビデオを通話および通話できます。 WiFi の使用状況の設定によって、ユーザーのモバイル デバイスが携帯データ ネットワーク上で WiFi ネットワークを使用する必要が生じするかどうかが決わります。
  
モビリティ、[通話]、および VoIP とビデオの機能はすべて、既定で有効になっています。 VoIP とビデオに WiFi を要求する設定は無効です。 管理者は、グローバル、サイト別、またはユーザー別にこれを変更できます。
  
モビリティ機能と [仕事から通話] を使用するには、次の条件を使用する必要があります。
  
- Skype for Business Server に対して有効
    
- エンタープライズ VoIP。
    
- **EnableMobility** オプションが True に設定されているモビリティ ポリシーが割り当 **てられている**。
    
ユーザーが [仕事から通話] を使用するには、次の条件も必要です。
  
- [電話の同時呼び出しを有効にする] オプションが選択されている音声ポリシー **が割り** 当て済み。
    
- **EnableOutsideVoice** が True に設定されているモビリティ ポリシーが割り当 **てられている**。
    
> [!NOTE]
> エンタープライズ VoIP が有効になっていないユーザーは、関連付けられている音声ポリシーに適切なオプションが設定されている場合、モバイル デバイスで Skype と Skype の VoIP 通話を行う場合や、モバイル デバイスで [クリックして参加] リンクを使用して会議に参加できます。 計画に関するトピックの詳細について説明します。 
  
### <a name="modify-global-mobility-policy"></a>グローバル モビリティ ポリシーの変更

1. **CsAdministrator** の役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. 次のように入力して、Mobility and Call via Work へのアクセスをグローバルにオフにします。
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Mobility へのアクセスをオフにすることなく、"仕事から通話" をオフにできます。 ただし、[仕事から通話] もオフにしない場合、Mobility をオフに設定できます。 
  
    詳しくは [、Set-CsMobilityPolicy をご覧ください](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>サイト別にモビリティ ポリシーを変更する

1. **CsAdministrator** の役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. サイト レベルのポリシーの作成、VoIP とビデオのオフ、IP オーディオに WiFi の要求、サイト別の IP ビデオの WiFi の要求を有効にできます。 種類:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    詳細については [、「New-CsMobilityPolicy」を参照してください](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>ユーザー別にモビリティ ポリシーを変更する

1. **CsAdministrator** の役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. ユーザー レベルのモビリティ ポリシーを作成し、モビリティと [仕事から通話] をユーザー別にオフにします。 種類:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    サンプル データを使用したその他の例:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Mobility へのアクセスをオフにすることなく、"仕事から通話" をオフにできます。 ただし、[仕事から通話] もオフにしない場合、Mobility をオフに設定できます。 
  

