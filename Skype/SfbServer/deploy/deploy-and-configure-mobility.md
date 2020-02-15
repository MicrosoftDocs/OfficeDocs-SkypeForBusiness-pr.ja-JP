---
title: Skype for Business Server のモビリティを展開および構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: この記事では、モビリティサービスを使用するように既存の Skype for Business Server のインストールを構成する手順について説明します。これにより、モバイルデバイスで Skype for Business Server のモビリティ機能を利用できるようになります。
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029068"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Skype for Business Server のモビリティを展開および構成する  
 
この記事では、モビリティサービスを使用するように既存の Skype for Business Server のインストールを構成する手順について説明します。これにより、モバイルデバイスで Skype for Business Server のモビリティ機能を利用できるようになります。
  
Skype for business [server のモビリティの計画](../plan-your-deployment/mobility.md)を確認したら、以下の手順を続行して、モビリティを Skype For business server 環境に展開する準備ができている必要があります。 手順は次のとおりです (この表には、アクセス許可の一覧が含まれています)。
  
|**フェーズ**|**アクセス許可**|
|:-----|:-----|
|[DNS レコードを作成する](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Domain Admins  <br/> DNSAdmins  <br/> |
|[証明書を変更する](deploy-and-configure-mobility.md#ModCerts) <br/> |ローカル管理者  <br/> |
|[リバース プロキシを構成する](deploy-and-configure-mobility.md#ConfigRP) <br/> |ローカル管理者  <br/> |
|[ハイブリッド展開によるモビリティの自動検出の構成](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Domain Admins  <br/> |
|[モビリティ展開をテストする](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[プッシュ通知を構成する](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[モビリティポリシーを構成する](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
以降のすべてのセクションには、計画のトピックを読んでいることを前提とする手順が含まれています。 混乱が生じた場合は、その情報を自由に確認してください。

> [!NOTE]
> 従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。 現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。
  
## <a name="create-dns-records"></a>DNS レコードを作成する
<a name="CreateDNSRec"> </a>

これらは、既に Skype for Business Server 環境の一部として用意されている場合がありますが、自動検出を動作させるには、次のレコードを作成する必要があります。
  
- 組織のネットワーク内から接続しているモバイルユーザーをサポートするための内部 DNS レコード。
    
- 組織のネットワーク外から接続しているモバイルユーザーをサポートするための外部 (またはパブリック) DNS レコード。
    
これらのレコードは、(ホスト) 名または CNAME レコードのいずれかにすることができます (両方の操作を行う必要はありません)。
  
### <a name="create-an-internal-dns-cname-record"></a>内部 DNS CNAME レコードを作成する

1. **Domain Admins**グループまたは**DnsAdmins**グループのメンバーである、ネットワーク内の DNS サーバーにログインします。
    
2. [**スタート**] ボタンをクリックし、[**管理ツール**] を選択します ([スタート] メニューからオプションが表示されていない場合に**検索**する必要がある場合があります)。次に、[ **DNS** ] をクリックして、dns 管理スナップインを開きます。
    
3. コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームとなるドメインに移動し、そこで**前方参照ゾーン**を展開する必要があります。
    
4. すぐに、次のどちらがあるか確認してください。
    
   - フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。
    
5. この点を確認したら、SIP ドメイン名を右クリックし、メニューから [**新しいエイリアス (CNAME)** ] を選択します。
    
6. [**エイリアス名**] テキストボックスに、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。
    
7. **完全修飾ドメイン名 (ターゲットホストの fqdn**) で、前の手順4で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の内部 WEB サービス fqdn を入力または参照する必要があります。 入力した場合は、[OK] をクリックします。
    
8. Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 CNAME レコードを作成する必要があります。
    
### <a name="create-an-external-dns-cname-record"></a>外部 DNS CNAME レコードを作成する

1. これらの手順は汎用的なものですが、使用しているパブリック DNS プロバイダーを知ることはできませんが、サポートが必要な場合もあります。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。
    
2. この時点で、Skype for Business Server には SIP ドメインが既に存在している必要があります。 この SIP ドメインの**前方参照ゾーン**を展開するか、またはそれを開きます。
    
3. すぐに、次のどちらがあるか確認してください。
    
   - フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。
    
4. この情報を取得すると、**新しいエイリアス (CNAME)** を作成するためのオプションを選択できるようになります。
    
5. これで、**エイリアス名**を入力できるようになります。外部自動検出サービス URL には、lyncdiscover を入力する必要があります。
    
6. 次に、**ターゲットホストの fqdn**に入力する領域が存在する必要があります。これは、前述の手順3で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の fqdn である必要があります。
    
7. ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の CNAME レコードを作成する必要がある場合は、この手順を実行する必要がありますが、準備が整ったら、作業を保存します。
    
### <a name="create-an-internal-dns-a-record"></a>内部 DNS A レコードを作成する

1. **Domain Admins**グループまたは**DnsAdmins**グループのメンバーである、ネットワーク内の DNS サーバーにログインします。
    
2. [**スタート**] ボタンをクリックし、[**管理ツール**] を選択します ([スタート] メニューからオプションが表示されていない場合に**検索**する必要がある場合があります)。次に、[ **DNS** ] をクリックして、dns 管理スナップインを開きます。
    
3. コンソールウィンドウの左側のウィンドウで、Skype for Business Server のフロントエンドサーバーのホームとなるドメインに移動し、そこで**前方参照ゾーン**を展開する必要があります。
    
4. すぐに、次のどちらがあるか確認してください。
    
   - フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。
    
5. この点を確認したら、SIP ドメイン名を右クリックし、メニューから [**新しいホスト (A または AAAA)** ] を選択します。
    
6. [**名前**] ボックスに、内部自動検出サービス URL のホスト名として「lyncdiscoverinternal」と入力します。
    
7. [ **IP アドレス**] テキストボックスに、前の手順4で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の内部 WEB サービス IP アドレスを入力します。
    
8. 完了したら、[**ホストの追加**] をクリックし、[ **OK**] をクリックします。
    
9. Skype for Business Server 環境でサポートされている各 SIP ドメインの前方参照ゾーンで、新しい自動検出 A または AAAA レコードを作成する必要があります。 これを行うには、必要に応じて、手順6-8 を繰り返します。
    
10. 完了したら、[**完了**] をクリックします。
    
### <a name="create-an-external-dns-a-record"></a>外部 DNS A レコードを作成する

1. これらの手順は汎用的なものですが、使用しているパブリック DNS プロバイダーを知ることはできませんが、サポートが必要な場合もあります。新しい DNS レコードを作成できるアカウントを使用して、パブリック DNS プロバイダーにログインしてください。
    
2. この時点で、Skype for Business Server には SIP ドメインが既に存在している必要があります。 この SIP ドメインの**前方参照ゾーン**を展開するか、またはそれを開きます。
    
3. すぐに、次のどちらがあるか確認してください。
    
   - フロントエンドサーバー (Standard または Enterprise) またはフロントエンドプールの任意のホスト A または AAAA レコード。
    
   - ディレクターまたはディレクタープールの任意のホスト A または AAAA レコード (展開でオプションとして使用できる構成)。
    
4. この情報を取得すると、**新しいホスト a または AAAA**を作成するためのオプションを選択できるようになります。
    
5. これで、**名前**を入力できるようになります。外部自動検出サービス URL には、lyncdiscover を入力する必要があります。
    
6. 次に、 **Ip Addresss**で入力する領域が必要になります。これは、前の手順3で確認したフロントエンドプール (または単一のフロントエンドサーバーまたはディレクタープールまたはディレクター) の IP である必要があります。
    
7. ここで保存する必要がある場合や、Skype for Business Server 環境の各 SIP ドメインの前方参照ゾーンで追加の A または AAAA レコードを作成する必要がある場合は、そのようにする必要があります。準備が整ったら、作業を保存します。
    
## <a name="modify-certificates"></a>証明書を変更する
<a name="ModCerts"> </a>

証明書の計画についてご質問がある場合は、「 [Skype for Business Server のモビリティの計画](../plan-your-deployment/mobility.md)」の記事で説明しています。 その点を確認したら、次の手順を実行します。
  
- 新しい証明書が必要ですか。
    
- 証明機関 (CA) から新しい証明書を要求します。
    
- PowerShell を使用して、インプレース証明書を置き換えて更新します。
    
- Microsoft 管理コンソール (MMC) の証明書スナップインを使用して証明書を確認する。
    
### <a name="do-i-need-new-certificates"></a>新しい証明書が必要ですか。

1. 最初に、どの証明書がインプレースになっているか、また必要なエントリがあるかどうかを確認して確認する必要がある場合があります。 そのためには、ローカル管理者のアカウントを使用して Skype for Business Server にログインする必要があります。 このアカウントには、これらの手順の一部についても、発行元の証明機関 (CA) に対する権限が必要な場合があります。
    
2. [Skype for Business Server 管理シェル] を開きます ([スタート] メニューまたはタスクバーに固定していない場合は、検索を使用して見つけることができます)。
    
3. 更新された証明書を追加する前に、どの証明書が割り当てられているかを知ることが重要になります。 そのため、コマンドで、次のように入力します。
    
   ```powershell
   Get-CsCertificate
   ```

4. 手順3の情報は、自分にとって一意です。 複数の用途に対して割り当てられた1つの証明書があるかどうか、または必要なさまざまなコンポーネントに対して異なる証明書が割り当てられているかどうかを判断するには、それを調べる必要があります。 **Use**パラメーターは、証明書がどのように使用されているかを示し、 **Thumbprint**パラメーターは、すべて同じ証明書、または複数の証明書があるかどうかを通知します。
    
5. 「計画」セクションで推奨されている SAN エントリがある場合は、問題ありません。 それ以外の場合は、新しい証明書、または (構成に応じて) 証明機関からの複数の証明書を要求する必要があります。
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>証明機関 (CA) から新しい証明書または証明書を要求する

1. どの SAN エントリを使用しているかを確認した後、 **1 つの証明書**があること (前述の手順を実行した後)、必要なすべてのエントリがないことがわかりました。 CA に対して新しい証明書の要求を行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 不足している自動検出サービス SAN (-Ca パラメーターを独自の証明機関パスに置き換えます):
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - これで、複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに、DomainName パラメーターを使用する必要があります。 また、DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 例としては、次のようになります (-Ca パラメーターを独自の証明機関パスで置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. または、どの SAN エントリを使用しているかを確認した後、必要なエントリがすべて含まれていない**複数の証明書**があることがわかりました。 CA に対して新しい証明書の要求を行う必要があります。 Skype for Business Server PowerShell を開きます。
    
   - 不足している自動検出サービス SAN (-Ca パラメーターを独自の証明機関パスに置き換えます):
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - これで、複数の SIP ドメインがある場合は、上記の例のように AllSipDomain パラメーターを使用することはできません。 代わりに、DomainName パラメーターを使用する必要があります。 また、DomainName パラメーターを使用する場合は、lyncdiscoverinternal および lyncdiscover レコードの FQDN を定義する必要があります。 例を示します (-Ca パラメーターを独自の証明機関パスで置き換える)。
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - CA によって新しい証明書が生成されたら、それらを割り当てる必要があります。
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用して証明書を割り当てる

- 上記の「新しい証明書を必要とする」セクションで見つけた内容に応じて、次の**いずれか**を実行する必要があります。
    
  - すべてに対して1つの証明書がある場合 (拇印が同一) の場合は、次のことを実行する必要があります。
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - 何らかの証明書を取得している場合 (拇印はすべて異なる)、代わりに次のように実行します。
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Microsoft 管理コンソール (MMC) での証明書の表示

1. MMC の証明書スナップインを使用して証明書を確認するオプションがあります。 検索に MMC と入力するだけで、アプリケーションオプションとしてポップアップ表示されます。
    
2. 証明書スナップインを追加するには、[**ファイル**] をクリックし、[**スナップインの追加と削除**] (または、キーボードショートカット**Ctrl + M**も動作します) をクリックする必要があります。 **証明書**は左側のウィンドウでオプションとなり、それを選択して**から、** [**次へ**] をクリックします。
    
3. ポップアップウィンドウで、表示する必要がある証明書をホームにしているコンピューターでこれを実行する可能性がある場合は、[**ローカルコンピューター** ] を選択したままにします。 リモートコンピューターで作業している場合は、ラジオボタンを**別のコンピューター**に変更し、そのコンピューターの FQDN を入力するか、[**参照**] ボタンを使用してそのコンピューターを AD 経由で検索します。 コンピューターを選択したら、[準備ができたら、**完了**] をクリックし**てから、** スナップインを MMC に追加する必要があります。
    
4. MMC の左側のウィンドウで、[**証明書**] セクションを展開します。 [**個人**] フォルダーも展開し、[**証明書**] を選択します。 これにより、このストア内の証明書が表示されます。
    
5. 表示する証明書を見つけて右クリックし、[**開く**] を選択する必要があります。
    
    > [!NOTE]
    > このような証明書を確認するには、どうすればよいですか。 これは、ファームのすべてに割り当てられている単一の証明書であるか、または既定の内部 Web サービスなど、さまざまな用途に対して複数の証明書がある場合があります。その場合は、複数の証明書を調べる必要があります。 複数の証明書の拇印は同じです。 
  
6. **証明書**ビューが表示されたら、[**詳細**] を選択します。 これにより、[**件名**] を選択したときに証明書のサブジェクト名が表示され、割り当てられたサブジェクト名と関連付けられたプロパティが表示されます。
    
7. **サブジェクトの別名**エントリを確認する必要もあります。 次のうちの1つまたは複数が見つかります。
    
   - このプールのプール名、またはプールでない場合は単一のサーバー名。
    
   - 証明書が割り当てられているサーバーの名前。
    
   - 簡単な URL レコード (通常はミーティングとダイヤルイン)。
    
   - Web サービス内部および Web サービスの外部名 (たとえば、webpool01.contoso.net、webpool01.contoso.com) は、トポロジビルダーおよび優先度のある Web サービスの選択肢に基づいて作成されます。
    
   - 既に割り当てられている場合は、lyncdiscover。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコード
    
     複数の証明書が割り当てられている場合は、複数の証明書をチェックする必要があります (上記の注を確認してください)。
    
8. そのため、lyncdiscover が見つかった場合。\<microsoft.rtc.management.xds.sipdomain\>および lyncdiscoverinternal。\<microsoft.rtc.management.xds.sipdomain\>レコードは既に構成されています。 MMC を閉じることができます。
    
9. 割り当てられていない場合は、新しい証明書の要求を作成するか (上記の説明に従って)、post 要求をインストールする必要があります (これについては、上記の PowerShell を使用することをお勧めします)。
    
## <a name="configure-the-reverse-proxy"></a>リバース プロキシを構成する
<a name="ConfigRP"> </a>

以下の手順は、厳密に従うことを意図したものではありません。 これは、以前のバージョンの製品では、「Threat Management Gateway (TMG) を構成する」を参照していて、それを使用していなかった場合は、そこから独自のバージョンを使用する必要があるということです。
  
TMG は Microsoft によって製品として提供されなくなりましたが、まだ構成が必要な場合は、「 [Lync Server 2013 の手順](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)」を参照してください。 しかし、次の情報は、リバースプロキシごとに特定のチュートリアル手順を提供できない場合でも、より一般的に役に立ちます。
  
次の2つの主な考慮事項があります。
  
- HTTPS を使用して最初の自動検出要求を実行しようとしていますか (お勧めします)。
    
  - Web 公開ルールを持っている場合は、それを変更する必要があります。
    
  - Web 公開ルールをまだ持っていない場合は、作成する必要があります。
    
- HTTP 経由で最初の自動検出要求を行う場合は、そのルールも作成または変更する必要があります。
    
> [!NOTE]
> **重要**プロキシタイムアウト値は、展開から展開までの数によって異なります。 クライアントにとって最適な環境を実現するために、展開を監視し、価値を変更する必要があります。 この値は、少なくとも200に設定できます。 ご使用の環境で Lync モバイルクライアントをサポートしている場合は、値を960に設定して、タイムアウト値が900である Office 365 からのプッシュ通知のタイムアウトを許可する必要があります。 この値が小さすぎると、クライアントの切断を回避するためにタイムアウト値を増やす必要があります。または、クライアントが切断された後に、プロキシ経由の接続が切断されることがなく、長時間になる場合は、数を減らす必要があります。 この値に対して適切な設定を判断するには、環境に適したものを監視し、基準にすることが唯一の方法です。
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>外部自動検出 SAN および URL の既存の web 公開ルールを変更する

1. リバースプロキシインターフェイスを開きます。
    
2. Web 公開ルールを見つけて、[編集] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブ上にある場合があります)。
    
3. この web 公開ルールが適用されている場所を示す領域が存在する必要があります。 サイトの受信サイトまたは要求に対してこのルールを変更する必要があります。 新しいエントリを**追加**します。
    
4. リバースプロキシの形式に応じて、自動検出サイトの名前 (使用する例は lyncdiscover.contoso.com) を入力し、[ **OK]** または [**保存**] をクリックします。
    
5. 自動検出 SAN エントリが含まれている新しい証明書が存在する可能性があります。 これは、リバースプロキシの設定に従って、をインストールして、使用するように構成する必要があります。 構成が完了したら、必ずすべてを保存してください。
    
6. リバースプロキシに**テスト**機能がある場合は、その機能を利用して、すべてが正しく動作することを確認してください。
    
7. ご使用の環境にディレクターまたはディレクタープールがある場合は、この手順を繰り返す必要があります (これは、2番目のルールがあることを意味します)。
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>外部自動検出 URL の web 公開ルールを作成する

1. リバースプロキシインターフェイスを開きます。
    
2. Web 公開ルールを作成するインターフェイス内の場所を特定して、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブ上にある場合があります)。 新しい web 公開ルールを作成するオプションを探している場合。
    
3. 通常は、次の情報を入力する必要があります。
    
   - **Name**: ルールの名前
    
   - **ルールの処理**: この例では、**許可**ルールとして、リバースプロキシを介して何かが渡されることができます。
    
   - 選択している**公開**ルールまたはオプションは、**単一の web サイトまたはロードバランサー**です。
    
   - 外部アクセスには**SSL**を使用する必要があり、そのオプションを選択します。
    
   - **内部発行**用のパスを公開し、フロントエンドプールのロードバランサーに外部 Web サービスの fqdn を入力する必要があります。または、使用している場合は、ディレクタープールのロードバランサーの fqdn を入力します。そのためには、例を sfb_pool01 します。
    
   - 公開するパス** /** として「*」を入力する必要がありますが、**元のホストヘッダーも転送**する必要があります。
    
   - **パブリックまたは外部の名前**の詳細または情報に関するオプションが表示されます。 入力できる場所は次のとおりです。
    
   - **要求を受け入れ**ますが、これはドメイン名にする必要があります。
    
   - **名前**については、「 **lyncdiscover** 」と入力してください。 <sipdomain>(これは外部自動検出サービス URL です)。 次に、フロントエンドプールの外部 Web サービス URL のルールを作成している場合は、フロントエンドプールの外部 Web サービスの FQDN (たとえば、lyncwebextpool01.contoso.com) を入力する必要があります。
    
   - **パス**オプションが表示されます。ここで、* を** /** 入力する必要があります。
    
   - 最新のパブリック証明書を使用して、 **SSL リスナー**を選択する必要があります。
    
   - **認証の委任**を [**委任しない**] に設定する必要がありますが、直接クライアント認証を許可する**必要**があります。
    
   - ルールは**すべてのユーザー**に設定する必要があります。
    
   - このルールを作成して続行できるようにするために必要な情報をすべて指定する必要があります。
    
4. **元のホストヘッダー**が転送されるようにする必要があります。
    
5. **Web サーバー**のポートも設定する必要があります。次の操作を行う必要があります。
    
   - **要求を HTTP ポートにリダイレクト**し、ポート番号を**8080**にする必要があります。
    
   - **SSL ポートに要求をリダイレクト**し、ポート番号を**4443**にする必要があります。
    
6. すべての構成が完了したら、それらを保存または適用し、ルールをテストする必要があります。
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>ポート80の web 公開ルールを作成する (オプション)

1. リバースプロキシインターフェイスを開きます。
    
2. Web 公開ルールを作成するインターフェイス内の場所を特定して、[**新規**作成] または [**作成**] オプションを選択する必要があります (リバースプロキシの構成によっては、メニューまたはタブ上にある場合があります)。 新しい web 公開ルールを作成するオプションを探している場合。
    
3. 通常は、次の情報を入力する必要があります。
    
   - **Name**: ルールの名前
    
   - **ルールの処理**: この例では、**許可**ルールとして、リバースプロキシを介して何かが渡されることができます。
    
   - 選択している**公開**ルールまたはオプションは、**単一の web サイトまたはロードバランサー**です。
    
   - 公開され**た Web サーバーまたはファームに接続するに**は、セキュリティで保護されていない接続を使用する必要があります。
    
   - **内部発行**用のパスを公開し、フロントエンドプールのロードバランサーの**VIP アドレス**の FQDN を入力する必要がある場合は、例として sfb_pool01 します。
    
   - 公開するパス** /** として「*」を入力する必要がありますが、**元のホストヘッダーも転送**する必要があります。
    
   - **パブリックまたは外部の名前**の詳細または情報に関するオプションが表示されます。 入力できる場所は次のとおりです。
    
   - **要求を受け入れ**ますが、これはドメイン名にする必要があります。
    
   - **名前**については、「 **lyncdiscover** 」と入力してください。 <sipdomain>(これは外部自動検出サービス URL です)。
    
   - **パス**オプションが表示されます。ここで、* を** /** 入力する必要があります。
    
   - Web リスナーを選択するか、リバースプロキシで作成することが必要になります。
    
   - **認証の委任**は**委任なし**に設定する必要がありますが、直接の**クライアント認証は許可しないでください**。
    
   - ルールは**すべてのユーザー**に設定する必要があります。
    
   - このルールを作成して続行できるようにするために必要な情報をすべて指定する必要があります。
    
4. **Web サーバー**のポートを設定する必要があります。次の手順を実行する必要があります。
    
   - **要求を HTTP ポートにリダイレクト**し、ポート番号を**8080**にする必要があります。
    
   - **SSL ポートに要求をリダイレクト**し、ポート番号を**4443**にする必要があります。
    
5. すべての構成が完了したら、それらを保存または適用し、ルールをテストする必要があります。
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>ハイブリッド展開によるモビリティの自動検出の構成
<a name="ConfigAutoD"> </a>

Skype for Business Server のハイブリッド環境は、オンプレミスの環境と O365 環境を組み合わせた環境です。 ハイブリッド環境で Skype for Business Server を使用している場合、自動検出サービスは、これらの環境のいずれかからユーザーを検索できる必要があります。
  
モバイルクライアントがユーザーの場所を検出できるようにするには、自動検出サービスを新しい uniform resource locator (URL) を使用して構成する必要があります。 手順は次のとおりです。
  
1. Skype for Business Server 管理シェルを開きます。
    
2. 次を実行して、Skype for Business Server 環境の属性**Proxyfqdn**の値を取得します。
    
   ```powershell
   Get-CsHostingProvider
   ```

3. その後もシェルウィンドウで、次を実行します。
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    [identity] は、共有 SIP アドレス スペースのドメイン名で置き換えます。
    
## <a name="test-your-mobility-deployment"></a>モビリティ展開をテストする
<a name="TestMobility"> </a>

Skype for Business Server Mobility Service と Skype for Business Server の自動検出サービスを展開したら、テストトランザクションを実行して、展開が正常に動作することを確認してください。 **Test-csucwaconference**を実行すると、2人のユーザーが会議で作成、参加、および通信できるかどうかをテストできます。 このテストを行うには、2人のユーザー (real または test) とその完全な資格情報が必要です。 このコマンドは、Skype for Business クライアントと Lync Server 2013 クライアントの両方に対して機能します。
  
Skype for Business Server 2015 の Lync Server 2010 クライアントでは、テストのために**test-csmcxp2pim**を実行する必要があります。 Lync Server 2010 ユーザーは、実際のユーザーまたは事前定義されたテストユーザーである必要があり、パスワード資格情報が必要になります。

> [!NOTE]
> 従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。 現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Skype for Business および Lync 2013 モバイルクライアントのテスト会議

1. **Skype For Business Server 管理シェル**および**ocscore**がインストールされている任意のコンピューターで、 **csadministrator**の役割のメンバーとしてログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します ([検索] で名前を入力するか、[**すべてのプログラム**] を選択します)。
    
3. コマンドラインで、次のように入力します。
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   スクリプトで資格情報を設定して、テストコマンドレットに渡すこともできます。 次に例を示します。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Lync 2010 モバイルクライアントのテスト会議

> [!NOTE]
> 従来のモバイルクライアントに対する MCX (Mobility Service) のサポートは、Skype for Business Server 2019 では利用できなくなりました。 現在の Skype for Business mobile クライアントはすべて、既に統合コミュニケーション Web API (UCWA) を使用して、インスタントメッセージング (IM)、プレゼンス、および連絡先をサポートしています。 MCX を使用しているレガシクライアントを使用しているユーザーは、現在のクライアントにアップグレードする必要があります。

1. **Skype For Business Server 管理シェル**および**ocscore**がインストールされている任意のコンピューターで、 **csadministrator**の役割のメンバーとしてログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します ([検索] で名前を入力するか、[**すべてのプログラム**] を選択します)。
    
3. コマンドラインで、次のように入力します。
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   スクリプトで資格情報を設定して、テストコマンドレットに渡すこともできます。 次に例を示します。
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

コマンドプロシージャをさらに詳しく確認するには、 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)および[test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)を確認してください。
  
## <a name="configure-for-push-notifications"></a>プッシュ通知を構成する
<a name="ConfigPush"> </a>

プッシュ通知は、バッジ、アイコン、または通知の形式で、Skype または Lync アプリが非アクティブな場合でもモバイルデバイスに送信できます。 プッシュ通知とは何ですか。 これらは、新しいまたは不在着信した IM 出席依頼や受信したボイスメールなどのイベント通知です。 Skype for Business Server Mobility service は、これらの通知をクラウドベースの Skype for business Server プッシュ通知サービスに送信します。これにより、Windows Phone ユーザーの Microsoft プッシュ通知サービス (MSNS) に通知が送信されます。
  
この機能は Lync Server 2013 から変更されていませんが、Skype for Business Server を使用している場合は、次の操作を行います。
  
- Skype for Business Server エッジサーバーの場合は、新しいホスティングプロバイダーである Microsoft Skype for Business Online を追加し、組織と Skype for Business Online の間のホスティングプロバイダーフェデレーションを設定します。
    
- **Set-Cspの設定**コマンドレットを実行して、プッシュ通知を有効にします。 既定では、プッシュ通知はオフになっています。
    
- フェデレーション構成とプッシュ通知をテストします。
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>プッシュ通知用に Skype for Business エッジサーバーを構成する

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. Skype for Business Server online ホスティングプロバイダーを追加します。
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   次に例を示します。
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > 1つのホスティングプロバイダーとの間に複数のフェデレーション関係を設定することはできません。 そのため、sipfed.online.lync.com とのフェデレーション関係を持つホスティングプロバイダーを既にセットアップしている場合は、ホスティングプロバイダーの id が SkypeOnline 以外のものであっても、別のホスティングプロバイダーを追加しないでください。 
  
4. Skype for Business Online の組織とプッシュ通知サービスとの間のホスティングプロバイダーフェデレーションを設定します。 コマンドラインで、次のように入力する必要があります。
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>プッシュ通知を有効にする

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。
    
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

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
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

## <a name="configure-mobility-policy"></a>モビリティポリシーを構成する
<a name="ConfigMob"> </a>

Skype for Business Server を使用すると、Mobility service を使用できるユーザーを決定したり、勤務先から通話、ボイスオーバー IP (VoIP)、ビデオを使用したり、VoIP またはビデオで Wi-fi が必要かどうかを確認したりできます。 [勤務先から通話] を使用すると、モバイルユーザーは電話を発信または受信するときに、携帯電話の番号ではなく勤務先の電話番号を使用できます。 回線の他の端部のユーザーには、そのモバイルユーザーの携帯電話番号が表示されないため、モバイルユーザーは発信通話料金を回避できます。 VoIP およびビデオが設定されている場合、ユーザーは VoIP 通話とビデオを行うことができます。 WiFi 使用法の設定では、ユーザーのモバイルデバイスで、携帯データネットワーク経由で WiFi ネットワークを使用する必要があるかどうかを決定します。
  
モビリティ、勤務先から通話、および VoIP およびビデオ機能はすべて、既定で有効になっています。 VoIP およびビデオ用に WiFi を必須にする設定は無効になっています。 管理者は、グローバル、サイト、またはユーザーのいずれかを変更することができます。
  
モビリティ機能を使用し、勤務先から通話できるようにするには、ユーザーは次のことを行う必要があります。
  
- Skype for Business Server に対して有効
    
- エンタープライズ Voip を有効にします。
    
- **EnableMobility**オプションが**True**に設定されているモビリティポリシーが割り当てられている。
    
ユーザーが [勤務先から通話] を使用できるようにするには、次のものも必要になります。
  
- [**電話の同時呼び出しを有効に**する] オプションがオンになっている音声ポリシーが割り当てられている。
    
- **EnableOutsideVoice**が**True**に設定されているモビリティポリシーが割り当てられている。
    
> [!NOTE]
> エンタープライズ Voip が有効になっていないユーザーは、モバイルデバイスを使用して、関連付けられている音声ポリシーに該当するオプションが設定されている場合は、自分のモバイルデバイスを使用して Skype for Business VoIP を通話したり、会議に参加したりすることができます。た. 詳細については、「計画」のトピックを参照してください。 
  
### <a name="modify-global-mobility-policy"></a>グローバルモビリティポリシーを変更する

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. 次のように入力して、モビリティへのアクセスをグローバルにオンにして、作業をグローバルに呼び出します。
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > モビリティへのアクセスをオフにすることなく、勤務先から通話をオフにすることができます。 しかし、勤務先から通話をオフにしなくても、モビリティをオフにすることはできません。 
  
    詳細については、「 [get-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)」を参照してください。
    
### <a name="modify-mobility-policy-by-site"></a>モビリティポリシーをサイト別に変更する

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. サイトレベルのポリシーを作成し、VoIP およびビデオをオフにして、IP オーディオに対して WiFi を必須にし、サイトごとに IP ビデオに WiFi を要求することができます。 種類:
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    詳細については[、「get-csmobilitypolicy」を](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)参照してください。
    
### <a name="modify-mobility-policy-by-user"></a>モビリティポリシーをユーザー別に変更する

1. **Skype For Business Server 管理シェル**と**ocscore**がインストールされているコンピューターに、 **csadministrator**の役割のメンバーであるアカウントを使用してログオンします。
    
2. **Skype For Business Server 管理シェル**を起動します。
    
3. ユーザーレベルのモビリティポリシーを作成し、ユーザーの勤務時間外でモビリティをオフにします。 種類:
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    サンプルデータの例を次に示します。
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > モビリティへのアクセスをオフにすることなく、勤務先から通話をオフにすることができます。 しかし、勤務先から通話をオフにしなくても、モビリティをオフにすることはできません。 
  

