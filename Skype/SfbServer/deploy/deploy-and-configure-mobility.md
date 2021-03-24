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
description: この記事では、モバイル デバイスが Skype for Business Server モビリティ機能を利用できるように、モビリティ サービスを使用する既存の Skype for Business Server インストールを構成する手順について説明します。
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103863"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Skype for Business Server のモビリティの展開と構成  
 
この記事では、モバイル デバイスが Skype for Business Server モビリティ機能を利用できるように、モビリティ サービスを使用する既存の Skype for Business Server インストールを構成する手順について説明します。
  
「Plan [for Mobility for Skype for Business Server」](../plan-your-deployment/mobility.md) の記事を確認した後、以下の手順に進み、Skype for Business Server 環境に Mobility を展開する準備ができました。 手順は次のとおりです (この表にアクセス許可の一覧を含めます)。
  
|**フェーズ**|**アクセス許可**|
|:-----|:-----|
|[DNS レコードの作成](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[証明書を変更する](deploy-and-configure-mobility.md#ModCerts) <br/> |ローカル管理者  <br/> |
|[リバース プロキシを構成する](deploy-and-configure-mobility.md#ConfigRP) <br/> |ローカル管理者  <br/> |
|[ハイブリッド展開を使用してモビリティの自動検出を構成する](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[モビリティの展開をテストする](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[プッシュ通知を構成する](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[モビリティ ポリシーの構成](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
以下のすべてのセクションには、「計画」トピックを読んだと仮定した手順が含まれます。 何かわかりにくい場合は、その情報を自由に確認してください。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="create-dns-records"></a>DNS レコードの作成
<a name="CreateDNSRec"> </a>

Skype for Business Server 環境の一部として既にこれらを使用している場合がありますが、自動検出が機能するには、次のレコードを作成する必要があります。
  
- 組織のネットワーク内から接続しているモバイル ユーザーをサポートする内部 DNS レコード。
    
- 組織のネットワーク外から接続しているモバイル ユーザーをサポートする外部 (またはパブリック) DNS レコード。
    
これらのレコードには、A (ホスト) 名または CNAME レコードのいずれかを指定できます (両方を作成する必要はありません。ここでは、すべての手順を含むだけです)。
  
### <a name="create-an-internal-dns-cname-record"></a>内部 DNS CNAME レコードの作成

1. ドメイン管理者グループまたは **DnsAdmins** グループのメンバーであるネットワーク内の **DNS サーバーにログイン** します。
    
2. [**スタート]** ボタン、[管理ツールの選択]  **([** スタート] メニューのオプションではない場合は検索が必要な場合があります **)、[DNS]** をクリックして DNS 管理スナップインを開きます。
    
3. コンソール ウィンドウの左側のウィンドウで、Skype for Business Server のフロント エンド サーバーがあるドメインに移動し、そこに [前方参照領域] を展開する **必要** があります。
    
4. 少し時間を取って、次の中のどちらを使用しているのか確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。
    
   - ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。
    
5. これを確認したら、SIP ドメイン名を右クリックし、メニューから **[新しいエイリアス ] (CNAME)** を選択します。
    
6. [エイリアス名 **] テキスト** ボックスに、内部自動検出サービスの URL に「lyncdiscoverinternal」と入力します。
    
7. 上記の手順 4 で示した完全修飾ドメイン名 (ターゲット ホストの **FQDN)** で、フロント エンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の内部 Web サービス FQDN を入力または参照する必要があります。 これが入力された場合は、[OK] をクリックします。
    
8. Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照領域に新しい自動検出 CNAME レコードを作成する必要があります。
    
### <a name="create-an-external-dns-cname-record"></a>外部 DNS CNAME レコードの作成

1. これらの手順は、使用しているパブリック DNS プロバイダーを特定できないので、一般的ですが、引き続きお手伝いしたいと考えられます。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。
    
2. この時点で、Skype for Business Server 用の SIP ドメインが既に存在している必要があります。 この SIP **ドメインの前方参照領域** を展開するか、それ以外の場合は開きます。
    
3. 少し時間を取って、次の中のどちらを使用しているのか確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。
    
   - ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。
    
4. その情報を取得したら、新しいエイリアス (CNAME) を作成するためのオプション **を選択できる必要があります**。
    
5. これで、エイリアス名を入力できる **必要** があります。外部自動検出サービスの URL については、ここで lyncdiscover を入力する必要があります。
    
6. 次に、ターゲット ホストの FQDN に入力する領域が必要です。これは、上記の手順 3 で示したフロントエンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の **FQDN** である必要があります。
    
7. ここで保存する必要がある場合や、Skype for Business Server 環境内の各 SIP ドメインの前方参照領域に追加の CNAME レコードを作成する必要がある場合は、これを行う必要がありますが、準備ができたら作業を保存します。
    
### <a name="create-an-internal-dns-a-record"></a>内部 DNS A レコードを作成する

1. ドメイン管理者グループまたは **DnsAdmins** グループのメンバーであるネットワーク内の **DNS サーバーにログイン** します。
    
2. [**スタート]** ボタン、[管理ツールの選択]  **([** スタート] メニューのオプションではない場合は検索が必要な場合があります **)、[DNS]** をクリックして DNS 管理スナップインを開きます。
    
3. コンソール ウィンドウの左側のウィンドウで、Skype for Business Server のフロント エンド サーバーがあるドメインに移動し、そこに [前方参照領域] を展開する **必要** があります。
    
4. 少し時間を取って、次の中のどちらを使用しているのか確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。
    
   - ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。
    
5. これを確認したら、SIP ドメイン名を右クリックし、メニューから [新しいホスト (A または **AAAA)]** を選択します。
    
6. [名前 **] テキスト** ボックスに、ホスト名の lyncdiscoverinternal と入力し、内部自動検出サービスの URL を入力します。
    
7. **[IP アドレス] テキスト** ボックスに、上記の手順 4 で示したフロントエンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の内部 Web サービス IP アドレスを入力します。
    
8. これが完了したら、[ホストの追加] **をクリック** し **、[OK] をクリックします**。
    
9. Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照領域に新しい自動検出 A または AAAA レコードを作成する必要があります。 これを行うには、必要に応じて手順 6 ~ 8 を何度も繰り返します。
    
10. 完了したら、[完了] を **クリックします**。
    
### <a name="create-an-external-dns-a-record"></a>外部 DNS A レコードを作成する

1. これらの手順は、使用しているパブリック DNS プロバイダーを特定できないので、一般的ですが、引き続きお手伝いしたいと考えられます。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。
    
2. この時点で、Skype for Business Server 用の SIP ドメインが既に存在している必要があります。 この SIP **ドメインの前方参照領域** を展開するか、それ以外の場合は開きます。
    
3. 少し時間を取って、次の中のどちらを使用しているのか確認してください。
    
   - フロントエンド サーバー (Standard または Enterprise) またはフロント エンド プールのホスト A または AAAA レコード。
    
   - ディレクター プールまたはディレクター プールのホスト A または AAAA レコード (展開に必要なオプションの構成)。
    
4. その情報を取得したら、新しいホスト A または AAAA を作成するためのオプション **を選択できる必要があります**。
    
5. これで、名前を入力 **できる必要があります**。外部自動検出サービスの URL については、ここで lyncdiscover を入力する必要があります。
    
6. **次に、IP** アドレスに入力する領域が必要です。これは、上記の手順 3 で示したフロントエンド プール (または単一のフロント エンド サーバー、またはディレクター プールまたはディレクター) の IP である必要があります。
    
7. ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照領域に追加の A レコードまたは AAAA レコードを作成する必要がある場合は、これを行う必要がありますが、準備ができたら作業を保存します。
    
## <a name="modify-certificates"></a>証明書を変更する
<a name="ModCerts"> </a>

証明書の計画に関する質問がある場合は [、「Plan for Mobility for Skype for Business Server」の記事に記載](../plan-your-deployment/mobility.md) されています。 その確認が完了したら、次の手順を実行します。
  
- 新しい証明書が必要ですか?
    
- 証明機関 (CA) からの新しい証明書の要求。
    
- PowerShell を使用して置換を使用してインプレイス証明書を更新します。
    
- Microsoft 管理コンソール (MMC) で証明書スナップインを使用して証明書を確認します。
    
### <a name="do-i-need-new-certificates"></a>新しい証明書が必要ですか?

1. 最初に、どの証明書がインプレイスで、必要なエントリを持っているかどうかを確認し、確認する必要があります。 これを行うには、ローカル管理者であるアカウントを使用して Skype for Business Server にログインする必要があります。 また、このアカウントには、発行元証明機関 (CA) に対する権限が必要な場合があります。これらの手順の一部について説明します。
    
2. Skype for Business Server 管理シェルを開きます ([スタート] メニューまたはタスク バーにピン留めされていない場合は、検索を使用して検索できます)。
    
3. 更新された証明書を追加する前に、割り当てられている証明書を知る必要があります。 コマンドで次のコマンドを入力します。
    
   ```powershell
   Get-CsCertificate
   ```

4. 手順 3 の情報は、ユーザーに固有の情報です。 複数の証明書に割り当てられている証明書が 1 つなのか、必要なコンポーネントごとに異なる証明書が割り当てられているのかを確認するには、その証明書を確認する必要があります。 **Use パラメーター** は、証明書の使用方法を示し、**拇** 印パラメーターは、証明書が同じ証明書か複数の証明書かを示します。
    
5. [計画] セクションで推奨される SAN エントリがある場合は、適切です。 存在しない場合は、新しい証明書、または複数の証明書 (構成に応じて) を証明機関から要求する必要があります。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>証明機関 (CA) から新しい証明書または証明書を要求する

1. 自分が持っている SAN エントリを確認した後、(上記の手順で確認した後で) 1 つの証明書を持っているのが分かっています。必要なすべてのエントリを持っている必要はないと学習しました。 CA に対して新しい証明書要求を行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 不足している自動検出サービス SAN の場合 (-Ca パラメーターを独自の証明機関パスに置き換える):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。 たとえば、次のようになります (-Ca パラメーターを独自の証明機関パスに置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. または、自分が持っている SAN エントリを確認した後、必要なすべてのエントリを持っていない複数の証明書が見つかりました。 CA に対して新しい証明書要求を行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 不足している自動検出サービス SAN の場合 (-Ca パラメーターを独自の証明機関パスに置き換える):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - 複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに DomainName パラメーターを使用する必要があります。 DomainName パラメーターを使用する場合は、lyncdiscoverinternal レコードと lyncdiscover レコードの FQDN を定義する必要があります。 例は次のようになります (-Ca パラメーターを独自の証明機関パスに置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA によって新しい証明書が生成されると、それらを割り当てる必要があります。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して証明書を割り当てる

- 上記の [新しい認定が必要な場合] セクションで見つけた内容に応じて、次のいずれかを実行 **する** 必要があります。
    
  - すべての証明書が 1 つ (拇印が同一) の場合は、次のコマンドを実行する必要があります。
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 異なる証明書がある場合 (拇印はすべて異なります)、代わりに次のコマンドを実行します。
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Microsoft 管理コンソール (MMC) での証明書の表示

1. MMC の証明書スナップインを使用して証明書を確認するオプションがあります。 MMC を検索に入力するだけで、アプリケーション オプションとしてポップアップ表示されます。
    
2. 証明書スナップインを追加するには、[ファイル] をクリックし、[スナップインの追加 **と削除]** をクリックする必要があります。(またはキーボード ショートカット Ctrl **+ M** も機能します)。 **左側の** ウィンドウで証明書を選択し、ポップアップ ウィンドウで [ **コンピューター** アカウント] を選択し、[次へ] の順に **選択します**。
    
3. それでも、ポップアップ ウィンドウでは、確認する必要がある証明書が保存されているコンピューターでこれを行う可能性が高いので、ローカル コンピューターで選択したままにします。そうである場合は、ローカル コンピューターで選択を残します。 リモート コンピューターで作業している場合は、ラジオ ボタンを [別のコンピューター] に変更し、そのコンピューターの FQDNを入力するか、[参照] ボタンを使用して AD を通じてそのコンピューターを検索します。 コンピューターを選択した後、準備ができたら [完了]をクリックし **、[OK]** をクリックしてスナップインを MMC に追加する必要があります。
    
4. MMC **の左側** のウィンドウで [証明書] セクションを展開します。 [個人用] **フォルダーも** 展開し、[証明書] **を選択します**。 これにより、このストアに証明書を表示できます。
    
5. 表示する証明書を見つけて右クリックし、[開く] を選択する必要 **があります**。
    
    > [!NOTE]
    > これが何の証明書かを知る方法は? ファームのすべてに割り当てられた単一の証明書か、Default、Internal Web Services など、さまざまなものに対して複数の証明書を持つ必要があります。その場合は、複数の証明書を確認する必要があります。 複数の証明書が同じ拇印を持つ。 
  
6. [証明書] ビューにアクセスしたら **、[詳細** ] を **選択します**。 これにより、[サブジェクト] を選択すると証明書のサブジェクト名が表示され、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。
    
7. サブジェクト代替名エントリも確認 **する** 必要があります。 次の 1 つ以上の情報が表示されます。
    
   - このプールのプール名、またはプールではない場合は単一のサーバー名。
    
   - 証明書が割り当てられているサーバー名。
    
   - 単純な URL レコード (通常は会議とダイヤルイン)。
    
   - トポロジ ビルダーおよび過剰な Web サービスの選択で行われた選択に基づいて、Web サービスの内部および Web サービスの外部名 (webpool01.contoso.net、webpool01.contoso.com など)。
    
   - 既に割り当てられている場合は、lyncdiscover。\<sipdomain\> lyncdiscoverinternal。\<sipdomain\> レコード。
    
     複数の証明書が割り当てられている場合は、複数の証明書を確認する必要があります (上記のメモを確認してください)。
    
8. したがって、lyncdiscover が見つかった場合。\<sipdomain\> lyncdiscoverinternal。\<sipdomain\> レコードの場合は、既に構成済みです。 MMC を閉じできます。
    
9. 割り当てられていない場合は、新しい証明書要求 (上記で説明) を行う必要があります。または、要求後にインストールする必要があります (このため、上記の PowerShell を次に示す方法をお勧めします)。
    
## <a name="configure-the-reverse-proxy"></a>リバース プロキシを構成する
<a name="ConfigRP"> </a>

以下の手順は、正確に従う必要があるという意味ではありません。 これは、以前のバージョンの製品では、たとえば、脅威管理ゲートウェイ (TMG) の構成などについて説明し、それを使用しない場合は、そこから独自のバージョンを作成する必要があるためです。
  
TMG は製品として Microsoft によって提供されなくなりました。それでも構成する必要がある場合は [、Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)の手順を確認できます。 ただし、以下の情報は、すべてのリバース プロキシに対して特定のウォークスルー 手順を提供する方法がない場合でも、より一般的に役立つ情報を提供することを目的としています。
  
考慮すべき主な点は次の 2 つがあります。
  
- HTTPS 経由で最初の自動検出要求を実行するつもりですか (推奨)
    
  - Web 発行ルールがある場合は、変更する必要があります。
    
  - Web 発行ルールがまだない場合は、作成する必要があります。
    
- HTTP で最初の自動検出要求を実行する場合は、そのルールも作成または変更する必要があります。
    
> [!NOTE]
> **重要** プロキシのタイム アウト値は、展開によって異なる数値です。 展開を監視し、クライアントに最適なエクスペリエンスを得る値を変更する必要があります。 値を 200 に設定できる場合があります。 環境で Lync モバイル クライアントをサポートしている場合は、Office 365 からのプッシュ通知のタイム アウトを許可する値を 960 に設定する必要があります。これは、タイム アウト値が 900 です。 値が小さすぎるとクライアントの切断を回避するために、タイム アウト値を大きくする必要がある可能性が非常に高く、プロキシ経由の接続が切断されないが、クライアントが切断された後に長くクリアする場合は、数を減らします。 環境に対して通常の状態を監視およびベース化する方法は、この値の適切な設定を決定する唯一の正確な方法です。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>外部自動検出 SAN と URL の既存の Web 発行ルールを変更する

1. リバース プロキシ インターフェイスを開きます。
    
2. Web 発行ルールを見つけて、[編集] オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブに表示される場合があります)。
    
3. この Web 発行ルールの適用条件を示す領域が必要です。 受信サイトまたはサイトの要求に対してこのルールを変更する必要があります。 新しいエントリを **追加** します。
    
4. 自動検出サイトの名前を入力し (使用する例は lyncdiscover.contoso.com)、リバース プロキシの形式に応じて **[OK]** または [保存] をクリックします。
    
5. 自動検出 SAN エントリを含む新しい証明書がある場合があります。 リバース プロキシの設定に従って使用するようにインストールして構成する必要があります。 構成が完了したら、必ずすべてを保存してください。
    
6. リバース プロキシにテスト機能 **がある** 場合は、その機能を利用して、すべてが正しく動作する必要があります。
    
7. ここで、環境にディレクター またはディレクター プールがある場合は、これらの手順を繰り返す必要があります (これは、2 番目のルールがあるという意味です)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>外部自動検出 URL の Web 発行ルールを作成する

1. リバース プロキシ インターフェイスを開きます。
    
2. Web 発行ルールを作成するインターフェイス内の場所を見つけて、[新規] または [作成]オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブにある場合があります)。 新しい Web 発行ルールを作成するオプションを探しています。
    
3. 通常、次の情報を入力する必要があります。
    
   - **名前**: ルールの名前
    
   - **ルールアクション**: この場合、 **許可ルールは** 、リバース プロキシを通過させるルールです。
    
   - 選択 **する発行** ルールまたはオプションは、単一 **の Web サイトまたはロード バランサーになります**。
    
   - これは、外部アクセス用 **の SSL** である必要があります。そのオプションを選択します。
    
   - 内部発行のパスを発行し、フロントエンド プールのロード バランサー (またはディレクター プールのロード バランサーの FQDN) に外部 Web サービスの FQDN を入力する必要があります。たとえば、sfb_pool01.contoso.local です。
    
   - 発行するパスとして _ と入力する必要がありますが、元のホスト ヘッダー **/\\** **を _*forward する必要があります。
    
   - パブリックまたは外部の名前の **詳細または情報の** オプションがあります。 これは、入力できる場所です。
    
   - **要求を受け** 入れるが、ドメイン名用である必要があります。
    
   - [名前 **] に****「lyncdiscover」と入力する必要があります。** <sipdomain> (これは外部自動検出サービスの URL です)。 ここで、フロントエンド プールに外部 Web サービス URL のルールを作成する場合は、フロントエンド プールの外部 Web サービスの FQDN を入力する必要があります (たとえば、lyncwebextpool01.contoso.com)。
    
   - [パス] オプション **が** 表示され、ここに * と入力 **/\\** する必要があります。
    
   - 最新のパブリック証明書を使用して **SSL リスナー** を選択する必要があります。
    
   - **認証委任は** [委任なし] **に設定する** 必要がありますが、直接 **クライアント認証を** 許可する必要があります。
    
   - ルールは [すべてのユーザー] **に設定する必要があります**。
    
   - これは、このルールを作成し、続行するために必要なすべての情報である必要があります。
    
4. 元のホスト ヘッダーが転送されるの **を確認する** 必要があります。
    
5. Web **サーバー ポート** も設定する必要があります。次の操作を行う必要があります。
    
   - **要求を HTTP ポートにリダイレクトし** 、ポート番号は **8080 である必要があります**。
    
   - **要求を SSL ポートにリダイレクトし** 、ポート番号は **4443 である必要があります**。
    
6. すべてが構成されている場合は、これらを保存または適用し、ルールをテストする必要があります。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>ポート 80 の Web 発行ルールを作成する (オプション)

1. リバース プロキシ インターフェイスを開きます。
    
2. Web 発行ルールを作成するインターフェイス内の場所を見つけて、[新規] または [作成]オプションを選択する必要があります (リバース プロキシの構成によっては、メニューまたはタブにある場合があります)。 新しい Web 発行ルールを作成するオプションを探しています。
    
3. 通常、次の情報を入力する必要があります。
    
   - **名前**: ルールの名前
    
   - **ルールアクション**: この場合、 **許可ルールは** 、リバース プロキシを通過させるルールです。
    
   - 選択 **する発行** ルールまたはオプションは、単一 **の Web サイトまたはロード バランサーになります**。
    
   - 公開された Web サーバーまたはファームに接続するには、セキュリティで保護されていない **接続である必要があります**。
    
   - 内部発行のパスを発行し、フロントエンド プールのロード バランサーの VIP アドレスの **FQDN** を入力する必要があります。例は sfb_pool01.contoso.local です。
    
   - 発行するパスとして _ と入力する必要がありますが、元のホスト ヘッダー **/\\** **を _*forward する必要があります。
    
   - パブリックまたは外部の名前の **詳細または情報の** オプションがあります。 これは、入力できる場所です。
    
   - **要求を受け** 入れるが、ドメイン名用である必要があります。
    
   - [名前 **] に****「lyncdiscover」と入力する必要があります。** <sipdomain> (これは外部自動検出サービスの URL です)。
    
   - [パス] オプション **が** 表示され、ここに * と入力 **/\\** する必要があります。
    
   - Web リスナーを選択するか、リバース プロキシで作成を許可する必要があります。
    
   - **[認証委任** ] を **[委任** なし] に設定する必要がありますが、直接クライアント認証 **は** 許可されません。
    
   - ルールは [すべてのユーザー] **に設定する必要があります**。
    
   - これは、このルールを作成し、続行するために必要なすべての情報である必要があります。
    
4. Web **サーバー ポート** を設定する必要があります。次の操作を行う必要があります。
    
   - **要求を HTTP ポートにリダイレクトし** 、ポート番号は **8080 である必要があります**。
    
   - **要求を SSL ポートにリダイレクトし** 、ポート番号は **4443 である必要があります**。
    
5. すべてが構成されている場合は、これらを保存または適用し、ルールをテストする必要があります。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>ハイブリッド展開を使用してモビリティの自動検出を構成する
<a name="ConfigAutoD"> </a>

Skype for Business Server のハイブリッド環境は、オンプレミス環境と O365 環境を組み合わせた環境です。 Skype for Business Server がハイブリッド環境で動作している場合、自動検出サービスは、これらの環境のどちらかからユーザーを見つけ出す必要があります。
  
モバイル クライアントがユーザーの場所を検出するには、自動検出サービスを新しい統一リソース ロケーター (URL) で構成する必要があります。 手順は次のとおりです。
  
1. Skype for Business Server 管理シェルを開きます。
    
2. 次のコマンドを実行して、Skype for Business Server 環境の **ProxyFQDN** 属性の値を取得します。
    
   ```powershell
   Get-CsHostingProvider
   ```

3. 次に、シェル ウィンドウで次のコマンドを実行します。
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    [identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。
    
## <a name="test-your-mobility-deployment"></a>モビリティの展開をテストする
<a name="TestMobility"> </a>

Skype for Business Server Mobility Service と Skype for Business Server Autodiscover Service を展開したら、テスト トランザクションを実行して、展開が正しく機能する必要があります。 **Test-CsUcwaConference** を実行して、2 人のユーザーが会議を作成、参加、通信する機能をテストできます。 このテストを実行するには、2 人のユーザー (実際またはテスト) と完全な資格情報が必要です。 このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方で機能します。
  
Skype for Business Server 2015 の Lync Server 2010 クライアントの場合は **、Test-CsMcxP2PIM** を実行してテストする必要があります。 Lync Server 2010 ユーザーは、実際のユーザー、または定義済みのテスト ユーザーである必要があります。パスワード資格情報が必要です。

> [!NOTE]
> 従来のモバイル クライアントの MCX (モビリティ サービス) サポートは、Skype for Business Server 2019 では利用できなくなりました。 現在のすべての Skype for Business モバイル クライアントはUnified Communications Web API (UCWA) を使用して、インスタント メッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用している従来のクライアントを持っているユーザーは、現在のクライアントにアップグレードする必要があります。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Skype for Business および Lync 2013 モバイル クライアントのテスト会議

1. **Skype for Business Server** Management Shell と **Ocscore** がインストールされている任意のコンピューターで **、CsAdministrator** 役割のメンバーとしてログオンします。
    
2. Skype **for Business Server 管理シェルを起動** します (検索に名前を入力するか、[すべてのプログラム] に移動 **して選択します** )。
    
3. コマンド ラインで、次のコマンドを入力します。
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   スクリプトで資格情報を設定し、テスト コマンドレットに渡す方法も可能です。 この例を以下に示します。
    
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

1. **Skype for Business Server** Management Shell と **Ocscore** がインストールされている任意のコンピューターで **、CsAdministrator** 役割のメンバーとしてログオンします。
    
2. Skype **for Business Server 管理シェルを起動** します (検索に名前を入力するか、[すべてのプログラム] に移動 **して選択します** )。
    
3. コマンド ラインで、次のコマンドを入力します。
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   スクリプトで資格情報を設定し、テスト コマンドレットに渡す方法も可能です。 この例を以下に示します。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

さらにコマンド手順を確認するには [、Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) と [Test-CsMcxP2PIM を確認できます](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。
  
## <a name="configure-for-push-notifications"></a>プッシュ通知を構成する
<a name="ConfigPush"> </a>

プッシュ通知は、バッジ、アイコン、またはアラートの形式で、Skype または Lync アプリが非アクティブな場合でもモバイル デバイスに送信できます。 しかし、プッシュ通知とは何ですか? これらは、新しい IM の招待や未承諾の IM 招待、または受信したボイスメールに関するイベント 通知です。 Skype for Business Server Mobility サービスは、これらの通知をクラウドベースの Skype for Business Server プッシュ通知サービスに送信し、Windows Phone ユーザー向け Microsoft プッシュ通知サービス (MSNS) に通知を送信します。
  
この機能は Lync Server 2013 から変更されませんが、Skype for Business Server を使用している場合は、次の操作を行う必要があります。
  
- Skype for Business Server エッジ サーバーの場合は、新しいホスティング プロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online 間のホスティング プロバイダー フェデレーションをセットアップします。
    
- **Set-CsPushNotificationConfiguration コマンドレットを実行してプッシュ通知を有効** にします。 既定では、プッシュ通知はオフになっています。
    
- フェデレーション構成とプッシュ通知をテストします。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>プッシュ通知用に Skype for Business エッジ サーバーを構成する

1. **CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
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
    > 1 つのホスティング プロバイダーと複数のフェデレーション関係を持つ必要があります。 したがって、sipfed.online.lync.com とのフェデレーション関係を持つホスティング プロバイダーを既にセットアップしている場合は、ホスティング プロバイダーの ID が SkypeOnline 以外の場合でも、別のホスティング プロバイダーを追加しない必要があります。 
  
4. Skype for Business Online で組織とプッシュ通知サービスの間のホスティング プロバイダー フェデレーションをセットアップします。 コマンド ラインで、次の入力が必要です。
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>プッシュ通知を有効にする

1. **CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. プッシュ通知を有効にする:
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. フェデレーションを有効にする:
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>フェデレーションとプッシュ通知のテスト

1. **CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
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

## <a name="configure-mobility-policy"></a>モビリティ ポリシーの構成
<a name="ConfigMob"> </a>

Skype for Business Server を使用して、モビリティ サービスを使用できるユーザー、仕事で通話できるユーザー、ボイス オーバー IP (VoIP)、ビデオ、および VoIP またはビデオに WiFi が必要かどうかを判断できます。 [仕事による通話] を使用すると、携帯電話の通話を送受信するときに、携帯電話番号の代わりに、モバイル ユーザーが自分の電話番号を使用できます。 回線のもう一方の端のユーザーは、そのモバイル ユーザーの携帯電話番号を表示し、モバイル ユーザーが発信通話料金を回避できます。 VoIP とビデオが設定されている場合、ユーザーは VoIP 通話とビデオを受け取って行います。 WiFi 使用状況の設定によって、ユーザーのモバイル デバイスが携帯電話データ ネットワークを使用して WiFi ネットワークを使用する必要が生じするかどうかを決定します。
  
モビリティ、仕事による通話、VoIP 機能とビデオ機能はすべて既定で有効になっています。 VoIP とビデオに WiFi を要求する設定は無効になっています。 管理者は、これをグローバルに、サイト別、またはユーザー別に変更できます。
  
モビリティ機能と仕事を通じて通話を使用するには、次の条件を使用する必要があります。
  
- Skype for Business Server で有効
    
- [有効] エンタープライズ VoIP。
    
- **EnableMobility** オプションが True に設定されているモビリティ ポリシーが割り当 **て済みです**。
    
ユーザーが仕事で通話を使用するには、次の機能も必要です。
  
- [電話の同時呼び出しを有効にする] オプションが選択されている音声ポリシー **が** 割り当てされました。
    
- **EnableOutsideVoice** が True に設定されているモビリティ ポリシーが割り当 **て済みです**。
    
> [!NOTE]
> エンタープライズ VoIP が有効になっていないユーザーは、モバイル デバイスを使用して Skype to Skype VoIP 通話を行い、または関連付けられている Voice ポリシーに対して適切なオプションが設定されている場合は、モバイル デバイスで [クリックして参加] リンクを使用して会議に参加できます。 PLANNING に関するトピックの詳細について説明します。 
  
### <a name="modify-global-mobility-policy"></a>グローバル モビリティ ポリシーの変更

1. **CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. 次のように入力して、Mobility と Call via Work へのアクセスをグローバルにオフにします。
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > モビリティへのアクセスをオフにすることなく、仕事で通話をオフにできます。 ただし、仕事で通話をオフにしない場合は、モビリティをオフに設定できます。 
  
    詳細については [、「Set-CsMobilityPolicy」を参照してください](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-site"></a>サイト別にモビリティ ポリシーを変更する

1. **CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. サイト レベルのポリシーを作成し、VoIP とビデオをオフにし、[IP オーディオに WiFi を要求する] と [サイト別 IP ビデオに WiFi を要求する] を有効にできます。 種類:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    詳細については [、「New-CsMobilityPolicy」を参照してください](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
    
### <a name="modify-mobility-policy-by-user"></a>ユーザーによるモビリティ ポリシーの変更

1. **CsAdministrator** 役割のメンバーであるアカウントを使用して **、Skype for Business Server 管理** シェルと **Ocscore** がインストールされているコンピューターにログオンします。
    
2. Skype **for Business Server 管理シェルを起動します**。
    
3. ユーザー レベルのモビリティ ポリシーを作成し、モビリティとユーザーによる仕事による通話をオフにします。 種類:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    サンプル データの追加例:
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > モビリティへのアクセスをオフにすることなく、仕事で通話をオフにできます。 ただし、仕事で通話をオフにしない場合は、モビリティをオフに設定できます。 
