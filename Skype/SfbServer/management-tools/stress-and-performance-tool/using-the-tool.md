---
title: Skype for Business Server 2015 Stress and Performance Tool の使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Skype for Business Server 2015 Stress and Performance Tool を実行するには、両側のユーザー、連絡先、およびユーザー プロファイルを管理できること、実行に備えてツールを構成できること、ツールによって生成された出力または結果を確認できることが必要です。
ms.openlocfilehash: af4d0dcb1cc4196f98941799c61dcf29510ba795
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992484"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool の使用
 
Skype for Business Server 2015 Stress and Performance Tool を実行するには、両側のユーザー、連絡先、およびユーザー プロファイルを管理できること、実行に備えてツールを構成できること、ツールによって生成された出力または結果を確認できることが必要です。
  
Skype for Business Server 2015 Stress and Performance Tool (実行可能ファイル名: LyncPerfTool.exe) の実行には、次の 4 区分の作業が必要になります。
  
- [ユーザーと連絡先の作成](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [ユーザー プロファイルの構成](using-the-tool.md#BKMK_UserProfile)
    
- [LyncPerfTool の実行](using-the-tool.md#BKMK_RunTool)
    
- [結果の解釈](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>ユーザーと連絡先の作成
<a name="BKMK_CreateUsersAndContacts"> </a>

Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) を使用して、ストレスおよびパフォーマンス テストのためのユーザーと連絡先を作成する必要があります。
  
次に示すリストは、このトピックを読み進めるときに役立つことがある便利な用語です。
  
- **Organizational Unit (組織単位)**: Active Directory Domain Services (AD DS) の組織単位 (OU)。
    
- **Federated/Cross Pool (フェデレーション/クロス プール)**: 別のインスタント メッセージング (IM) サービスのユーザーと通信できるユーザー。
    
- **配布リスト (Distribution List)**: DL。 AD DS ユーザーのリストを格納している AD DS のオブジェクトです。 ユーザー グループ間の通信を円滑に進めるために使用されます。
    
- **Location Info Service (場所情報サービス)**: Skype for Business Server 2015 のサービスであり、電話ごとに有効化および構成しておくと、Enhanced 911 (E911) サービスに対応する物理的な位置の取得が可能になります。
    
- **U.S. Phone Numbers (米国の電話番号)**: SIP URI と共にユーザーに割り当てられる電話番号であり、番号の逆引き検索 (RNL) で着信通話と発信通話をルーティングするために使用されます。
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>UserProvisioningTool.exe を使用してユーザーと連絡先を作成する

> [!NOTE]
> このツールを実行するために、Domain Admins セキュリティ グループのメンバーとしてログインしていることを作業の開始前に必ず確認してください。 これは、この作業で Active Directory ユーザーを作成することになるために必要な行動です。 
  
ロード シミュレーションのためのユーザーと連絡先を作成する場合は、Skype for Business Server User Provisioning Tool を使用する必要があります。
  
**Skype for Business Server User Provisioning Tool** は、**Skype for Business Server Stress and Performance Tool** パッケージと共にインストールされます。 このパッケージ インストーラー (CapacityPlanningTool.msi) は、テスト目的のフロント エンド サーバーまたは Standard Edition サーバーで実行しておきます。
  
Skype for Business Server User Provisioning Tool は、フロント エンド サーバーまたは Standard Edition サーバーで UserProvisioningTool.exe (%InstalledDirectory%LyncStressAndPerfTool\LyncStress にあります) を実行することで開始できます。
  
> [!IMPORTANT]
> 多数のユーザー (10,000 ユーザー以上) を作成するときには、UserProvisioningTool.exe を実行してください。 これは、このツールによって*新しい* AD ユーザーの作成と構成が実行されるために必要です。
  
User Provisioning Tool を起動したら、[Configuration] をクリックして [Load Configuration] を選択します。 
  
ユーザーと連絡先を構成するには、パッケージに含まれている "SampleData.xml" という既定のファイルを読み込みます。 これにより、各フィールドがサンプル データで再設定されます。ただし、それぞれの展開に応じて、このデータを変更する必要があります。
  
カスタマイズした設定が含まれている構成済みの XML ファイルがある場合は、そのファイルを読み込むことも可能です。 次の各セクションで説明するように、User Provisioning Tool のフィールドに入力します。
  
### <a name="to-configure-server-options"></a>サーバー オプションを構成するには:

1. **[Front End Pool FQDN]** フィールドに、Standard Edition サーバー、またはユーザーをホストするフロント エンド プールの完全修飾ドメイン名 (FQDN) を入力します。
    
2. **[User Name Prefix]** フィールドに、テスト目的のユーザー名を無効にする際に使用するプレフィックスを入力します ("TestUser" など)。
    
3. **[Password]** フィールドに、すべてのテスト ユーザー アカウントに使用するパスワードを入力します。
    
4. **[Account Domain]** フィールドに、現在の AD ドメインのドメイン名を入力します (テスト ユーザーの作成先にするドメイン)。
    
5. **[Organizational Unit]** フィールドに、該当するテスト ユーザーの作成先にする AD ドメインの名前を入力します  (この OU が存在していない場合は、自動的に作成されます)。
    
6. **[Phone Area Code]** フィールドに、すべてのテスト ユーザー アカウントに使用する 3 桁の市外局番を入力します。 ここで選択する市外局番は、AD 内の他のユーザーの市外局番と競合しないようにしてください。
    
7. **[Voice Enabled]** チェックボックスをクリックしてオンにします (テスト ユーザーがエンタープライズ VoIP を使用できるようにする場合)。
    
8. **[Number of Users]** フィールドでは、作成するテスト ユーザーの合計数を指定します。
    
9. **[Start Index]** フィールドでは、ユーザー名プレフィックスのサフィックスとして使用する最初の番号を指定します (次の例の場合、プレフィックスは "TestUser" になり、最初の名前の末尾は "0" になります)。
    
     ![[User Creation] タブを表示している User Provisioning Tool。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>[Create Users] ボタン

**[Create Users]** ボタンをクリックすると、入力した入力パラメーターが検証されます。 検証エラーが見つかると、そのエラーの修正を求められます。 すべての値が適切な場合は、AD (指定した OU 内) にユーザーが表示されるようになります。 ツールの実行時には、下側に進行状況バーが表示されます。 進行状況バーがアクティブになっている間は、アプリケーションを終了しないでください。
  
ユーザーの作成には時間がかかるため、それに応じて計画を立ててください。 この処理には、数分間 (ユーザーが少数の場合) から数時間 (ユーザーが多数の場合) かかることがあります。
  
テスト環境の AD ドメイン コントローラーにアクセスできない場合でも、作成対象に指定したユーザーの範囲内のいずれかのユーザーとしてログインすることで、ユーザーの作成を検証できます。 ユーザー名として、@sipDomain と共にプレフィックスとサフィックスを使用してください。 たとえば、<em>TestUser20@contoso.net</em> のようにします。
  
> [!NOTE]
> 既にユーザーが存在している場合に [Create Users] ボタンをクリックすると、そのユーザーは構成の変更内容によって更新されます。 
  
#### <a name="delete-users-button"></a>[Delete Users] ボタン

**[Delete Users]** ボタンをクリックすると、そのタブの入力パラメーターが検証されます。 検証エラーが見つかると、そのエラーの修正を求められます。入力値が適切な場合は、指定したテスト ユーザーが無効化され、Active Directory から削除されます。 前述したように、このタブの下側に進行状況バーが表示されます。この進行状況バーがアクティブになっている間はアプリケーションを終了しないでください。
  
> [!NOTE]
> 米国形式の電話番号のみがサポートされます。 ユーザーには電話番号が常に割り当てられます。また、UserProvisioningTool.exe で作成されたすべてのユーザーは、既定でエンタープライズ VoIP が有効化されます。 電話番号を使用するシナリオ (会議自動アテンダントや UC-PSTN 通話など) では、この電話番号が通話の正しいルーティングのために使用されます。 そのため、*すべてのユーザー*に*一意の電話番号*を用意する必要があります。
  
> [!NOTE]
> **ユーザーを 2 回作成する必要がある場合は、別の市外局番を使用するか、Disable-CsUser コマンドレットを使用して以前のユーザーを削除してください。それ以外の場合は、ユーザー作成のコマンドが失敗します。**
  
> [!IMPORTANT]
> 連絡先の作成前に、まず、ユーザーのレプリケーションを完了しておく必要があります (この操作は、[Users] タブで実行します)。 
  
> [!IMPORTANT]
> ユーザー作成の直後の場合は、Skype for Business Server レプリケーションが完了して、データベースにユーザー アカウントが設定されるまで、しばらくの間待機する必要があります。 **ユーザーのレプリケーションが完了していないと、エラーが表示されます。** ユーザーのレプリケーションの完了は、Skype for Business Server 2015 フロント エンド サービスが開始されていること、または指定した合計数の最後のユーザーに対する Get-CsUser コマンドレットが正常に実行されたことによって確認できます。
  
#### <a name="contacts-creation-tab"></a>[Contacts Creation] タブ

このタブを使用すると、テストのためのユーザーの連絡先詳細を指定できます。
  
![[Contents Creation] タブを表示している User Provisioning Tool。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>ユーザーの連絡先を構成するには、次の操作を実行します。

1. **[Average Contacts per User]** フィールドに、ユーザーごとの連絡先リストに設定する連絡先の平均数を入力します。
    
2. **[Fixed]** チェックボックスは、すべてのユーザーに同数の連絡先を作成する場合にオンにします。 各ユーザーに異なる数の連絡先を作成する場合は、このチェックボックスをオフにします。
    
3. **[Average Contact Groups per User]** フィールドに、ユーザーごとの連絡先グループの数を入力します。 この数は、**[Average Contacts per User]** よりも小さい数にする必要があります。
    
4. **[Federated / Cross Pool Contacts Percentage]** フィールドで、0 から 100 までの数を指定します。 この割合の連絡先が、フェデレーション ユーザーで作成されます。
    
5. **[Federated / Cross Pool User Prefix]** フィールドで、ローカル ユーザーの連絡先リストに追加するフェデレーション ユーザーのユーザー名を指定します。
    
6. **[Federated / Cross Pool User SIP Domain]** で、フェデレーション ユーザーの SIP ドメイン名を指定します。
    
7. **[User Creation]** タブで、情報に間違いがないことを確認します。 連絡先は、[User Creation] タブの各値に基づいて作成されます。
    
8. **[Create Contacts]** をクリックして、連絡先の作成を開始します。 この処理は、数分間かかります。 処理の完了後、"Operation Completed Successfully" というメッセージのダイアログ ボックスが表示されます。 作成した連絡先は、[User Creation] タブで作成したユーザーとしてログインすることで検証できます。
    
> [!NOTE]
> 連絡先の作成後、このツールによりターゲット プール内のすべてのフロント エンド サーバーが再起動されます。 フロント エンド サーバーの起動には長い時間がかかることがあります (最大 2 時間)。この時間は、この操作で作成した連絡先の数によって異なります。 
  
#### <a name="distribution-list"></a>配布リスト

Skype for Business Server 2015 Stress and Performance Tool では、Skype for Business 2015 クライアントの配布リスト (DL) 展開機能をシミュレートできます。 User Provisioning Tool で DL 展開を有効にしない場合は、この手順を省略できます。
  
![[Distribution List Creation] タブを表示している User Provisioning Tool。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
[Distribution List] タブでは、Stress and Performance Tool で配布リスト展開機能に使用される DL を作成できます。 DL の作成前に、Skype for Business Server 2015 を展開しておく必要があります。これには、ForestPrep の実行も含まれます。 この操作を実行していないと、DL の属性が AD スキーマに存在しないことになるため、このツールで DL を作成できなくなります。
  
### <a name="to-configure-distribution-lists"></a>配布リストを構成するには:

1. **[Number of Distribution Lists]** フィールドに、作成する DL の合計数を指定します (最初はユーザー数の倍の値にすることをお勧めします)。
    
2. **[Distribution List Prefix]** フィールドに、作成する DL のすべてに付加するプレフィックスを入力します (例: *testDL*)。 つまり、DL 数が 100 の場合、DL の名前は testDL0、testDL1 のようになり、最後は testDL99 になります。
    
3. **[Minimum Members in a Dist. List]** フィールドに、それぞれの DL に収めるユーザーの最小数を入力します。
    
4. **[Maximum Members in a Dist. List]** フィールドに、それぞれの DL に追加するユーザーの最大数を入力します。
    
#### <a name="create-distribution-lists-button"></a>[Create Distribution Lists] ボタン

[Create Distribution Lists] ボタンをクリックすると、このツールは Active Directory を照会して、配布リストが既存のプレフィックスと数に一致するかどうかが確認されます。 まだ存在していない DL については、ツールによって作成されます。 この新しく作成した配布リストにメンバーを追加するときには、[User Creation] タブで指定した範囲のユーザーが選択されます。
  
#### <a name="location-info-service-config-tab"></a>[Location Info Service Config] タブ

Skype for Business Server 2015 Stress and Performance Tool では、場所情報サービスに対応するダミーの構成ファイルを生成することもできます。 通常、場所情報サービスがサーバーのパフォーマンスに重大な影響を与えることはありません。 
  
![[Location Info Service Config] タブを表示している User Provisioning Tool。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
この機能をテストする場合は、フォームに値を入力してから [Generate LIS Config Files] ボタンをクリックします。これにより、次の .CSV ファイルが作成されます。
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
これらのファイルを LIS データベースにインポートする場合は、次の PowerShell コマンドレットを使用します。
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>ユーザー プロファイルの作成
<a name="BKMK_UserProfile"> </a>

ユーザーの作成後 (User Creation Tool を使用)、Skype for Business Server 2015 Load Configuration ツールを使用してユーザー プロファイルを構成できます。
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Skype for Business Server 2015 Load Configuration ツールの実行

Load Configuration ツール (UserProfileGenerator.exe) を起動して、各タブに入力します。 このツールでは、シミュレーションに必要なクライアント コンピューターごとにディレクトリを作成します。 それぞれのクライアント ディレクトリには、Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) を実行するためのスクリプトが付属します。 次からの各セクションでは、Skype for Business Server 2015 Load Configuration ツールの各タブにあるフィールドの入力例を示します。
  
> [!IMPORTANT]
> Load Configuration ツール (UserProfileGenerator.exe) で使用されるユーザー固有の値は、Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) でプールに指定した値と一致している必要があります。 
  
#### <a name="common-configuration-tab"></a>[Common Configuration] タブ

Load Configuration Tool の **[Common Configuration]** タブを次に示します。 次の各手順で説明するように、[Common Configuration] タブのフィールドを入力してください。
  
![[Common Configuration] タブを表示している [User Provisioning] タブ。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. **[Number of Available Machines]** フィールドに、Stress and Performance Tool (LyncPerfTool.exe) の実行に使用するコンピューターの数を入力します。 4500 ユーザーごとに 1 台のコンピューターを用意することをお勧めします。ただし、負荷レベルを下げる場合や、ツールで使用できる機能の一部のみを使用する場合、その数を変更してもかまいません (負荷レベルは、[General Scenarios] タブで設定します)。
    
2. **[Prefix for User Names]** フィールドに、すべてのユーザーのユーザー名フィールドに対するプレフィックスを入力します。 ログインするための Uniform Resource Identifier (URI) は、*ユーザーのプレフィックス[ユーザーの最初のインデックス …(ユーザー数-1)]@ユーザーのドメイン* になります (例: myUser009@Contoso.com)。
    
3. **[Password for All Users]** に、ユーザーの作成時に使用したパスワードを入力します。 このフィールドを空白のままにすると、ユーザー名がパスワードとして設定されます。
    
4. **[User Start Index]** フィールドに、構成する最初のユーザーのインデックスを入力します。 それぞれの種類または負荷のレベルごとに異なる範囲を構成できますが、構成対象の範囲ごとに Load Configuration ツール (UserProfileGenerator.exe) を 1 回実行する必要があります。
    
5. **[Number of Users]** フィールドに、構成するユーザーの合計数を入力します。
    
6. **[User Domain]** フィールドに、SIP URI に使用するドメインを入力します。 これは、各ユーザーが Skype for Business Server 2015 フロント エンド サーバーまたは Standard Edition サーバーにログオンするための SIP URI を構築する際に使用され、[Account Domain] とは異なることがあります。
    
7. **[Account Domain]** フィールドに、AD DS ドメイン ログオンを入力します。
    
8. **[MPOP Percentage]** (Multiple Point of Presence のパーセンテージ) フィールドには、複数のコンピューターまたはデバイスからログオンするユーザーの割合を指定します (たとえば、10 パーセントなど)。
    
9. 同時エンドポイントの最大数は、**[Sign in Per Second (per Instance)]** フィールドに入力します。 これは、ユーザーの最大ログイン数であり、毎秒 2 ログイン以下の割合 (<=2) にすることをお勧めします。
    
10. **[Access Proxy or Pool FQDN]** フィールドに、クライアントの接続先にするサーバーの完全修飾ドメイン名 (FQDN) を入力します。 ユーザーが外部的にログオンする場合は、アクセス プロキシを入力する必要があります。 ユーザーが内部の場合は、エンタープライズ プール サーバーまたは Standard Edition サーバーの FQDN を指定します。
    
11. **[Port]** フィールドに、ユーザーが SIP に使用するポートを入力します (既定値は 5061)。
    
12. **[External Network Server Settings]** フィールドには、[Access Proxy or Pool FQDN] と **[Port]** を再度指定します。 これらの設定は、外部エンドポイントのロード シミュレーションにのみ使用されます。
    
#### <a name="general-scenarios-tab"></a>[General Scenarios] タブ

![[General Scenarios] タブを表示している Load Configuration Tool。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
負荷レベルとパラメーターは、実行内容を決定することで示される一般的なシナリオごとに構成することも無効のままにすることもできます。 次に、一般的なオプションを示します。
  
> [!NOTE]
> [Local Information Services] 以外のすべてのフィールドの負荷レベルの値は、**[Disabled]**、**[Low]**、**[Medium]**、**[High]**、または **[Custom]** です。 [Disabled] 以外の設定を選択すると、クライアントごとの構成が生成されます。 [High] はサーバーでサポートされる最大負荷になります。[Medium] は最大負荷の 60%、[Low] は 30% になります。 
  
- **Instant Messaging**: ピアツーピアおよび会議通話が含まれます。適切な負荷レベルの値を選択します。
    
- **Audio Conferencing**: 会議通話*のみ*の負荷レベルを選択します。 ピアツーピア通話については、この後の「**Voice Scenarios**」セクションで説明します。 **[Advanced]** タブを開いて、マルチビューを有効にします。
    
- **Application Sharing**: アプリケーション共有の負荷レベルを選択します。
    
- **Data Collaboration**: データ コラボレーション (データ会議を含む) の負荷レベルを選択します。
    
- **Distribution List Expansion**: **[Advanced]** ボタンをクリックして、User Creation Tool (UserProvisioningTool.exe) の [DL] タブで構成したものと同じ値をフィールドに入力します。 負荷レベルを選択します。
    
- **Address Book Web Query**: アドレス帳の検索サービスです。アドレス帳ファイルのダウンロードではありません。 アドレス帳ファイルのダウンロードに対して有効にするには、**[Advanced]** ボタンをクリックして **[EnableABSDownload]** を True に設定します。 負荷レベルの値を指定します。
    
- **Response Group Service**: **[Advanced]** ボタンをクリックして、応答グループ サービスのエージェントのプロビジョニング時に作成した応答グループの URI を指定します。 少なくとも 1 つの応答グループを選択する必要があります。 それよりも多くの応答グループを使用する場合は、それらをセミコロンで区切ります。 実際の値になるように、**[RGSUriSuffixStartIndex]** と **[RGSUriSuffixEndIndex]** を更新します。 負荷レベルを選択します。
    
- **Location Information Services**: [Enabled] または [Disabled] のどちらかの負荷レベルを選択します。
    
> [!NOTE]
> それぞれのシナリオの横には [Advanced] ボタンがあります。また、既定の設定のバリエーションを有効にするチェックボックスのセットがあります。 
  
- *[Ad-hoc]* を選択すると、ツールによって 1 時間の間に作成される会議通話のシミュレーションが作成されます。
    
- *[Large Conf]* を選択すると、大規模な会議通話のシナリオがシミュレートされます。
    
-  *[External]* では、外部ユーザーについてもシミュレートするようにツールに指示します。
    
これらのボタンとチェックボックスは、それぞれのシナリオに固有な追加の値であり、Stress and Performance Tool の動作を変更して、カスタマイズを可能にします。
  
[General Scenarios] タブの各シナリオ ([Location Information Services] を除く) では、負荷レベルの値が **[Custom]** の場合、会話レートが [Advanced] ダイアログ ボックスの対応するフィールドを使用して計算されます。 フィールド名はシナリオによって異なることがありますが、フィールドの説明には、*[NOTE This number will only be used if Custom is selected from the drop-down menu]* (注: この数値は、ドロップダウン メニューから [Custom] を選択した場合にのみ使用されます) と示されます。
  
**[High]**、**[Medium]**、および **[Low]** の値は、すべてのシナリオのバランスを取ったユーザー モデルに合せてモダリティごとの会話レートを変更します。 想定される使用状況とは異なるために、モダリティごとの負荷レベルを変更する必要がある場合は、[Custom] の会話レートを使用します。
  
#### <a name="voice-scenarios-tab"></a>[Voice Scenarios] タブ

このタブでは、すべての音声関連のシナリオを構成します。
  
![Load Configuration Tool の [Voice Scenarios] タブ。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
オプションは次のとおりです。
  
- **[VoIP]**: **[Advanced]** ボタンをクリックして、[PhoneAreaCode] と [LocationProfile (dial plan)] フィールドの値を追加します。 また、負荷レベルの値も指定します。 [VoIP] または [UC/PSTN Gateway] の負荷レベルを有効にすると、外部通話をシミュレートするために、公衆交換電話網 (PSTN) から統合コミュニケーション (UC) への構成ファイルが生成されます。
    
- **UC/PSTN Gateway**: 負荷レベルの値を選択する必要があり、[Disabled] 以外の値を選択した場合は、**[Advanced]** ボタンをクリックして PSTN 市外局番の値も指定します。 [Mediation Server and PSTN] の下側にある **[Add]** をクリックします。 その市外局番のルートが構成されていることを確認してください。
    
    > [!TIP]
    > Skype for Business コントロール パネルまたは Skype for Business 管理シェルを使用すると、音声ルートの構成を確認できます。 
  
- **Conferencing Attendant**: 負荷レベルの値を指定します。 [Disabled] 以外の値にすると、**[Telephone Number]** フィールドが有効になります。 使用する自動応答の電話番号を入力します。 **[Advanced]** をクリックして、**[LocationProfile]** フィールドの値を指定します。
    
- **Call Parking Service**: 負荷レベルを指定します。
    
- **Mediation Server and PSTN**: 使用する仲介サーバーごとに独自の PSTN シミュレーターが必要です。 シミュレーターに使用するクライアントを決定したら、構成した PSTN シミュレーターで、そのコンピューターに通話をルーティングするように仲介サーバーを構成します。 **[Add]** ボタンをクリックして、仲介サーバーの値を構成します。
    
    > [!NOTE]
    > それぞれのシナリオの横には [Advanced] ボタンがあります。 [Advanced] ダイアログ ボックスには、Stress and Performance Tool の動作を変更してカスタマイズを可能にする、各シナリオに固有の設定が含まれています。 > [Voice Scenarios] タブの各シナリオでは、負荷レベルの値が **[Custom]** の場合、会話レートが [Advanced] ダイアログ ボックスの対応するフィールドを使用して計算されます。 フィールド名はシナリオによって異なることがありますが、フィールドの説明には、*[NOTE This number will only be used if Custom is selected from the drop-down menu]* (注: この数値は、ドロップダウン メニューから [Custom] を選択した場合にのみ使用されます) と示されます。
  
#### <a name="web-app-tab"></a>[Web App] タブ

![Load Configuration Tool の [Web app] タブ。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
[Web App] では、フロント エンド サーバーにインストールされた Unified Communications Web API (UCWA) サーバーによる会議シナリオをサポートします。 [Web App] タブを使用して、Web アプリ関連のすべてのシナリオを構成します。 オプションは、次のとおりです。
  
- **General Web App Settings**: **[Additional Settings]** ボタンをクリックして、**[ReachTargetServerUrl]** をフロント エンド プール VIP のディレクトリ プール仮想 IP (VIP) に設定します。
    
- **Application Sharing**: 負荷レベルの値を選択します。
    
- **Data Collaboration**: 負荷レベルの値を選択します。
    
- **Instant Messaging**: 負荷レベルの値を選択します。
    
- **Voice Conferencing**: 負荷レベルの値を選択します。
    
> [!NOTE]
> それぞれのシナリオの横には **[Advanced]** ボタンが配置されています。 [Advanced] ダイアログには、Stress and Performance Tool の動作を変更してカスタマイズを可能にする、各シナリオに固有の値が含まれています。> それぞれの [Web App] のシナリオについて、負荷レベルが **[Custom]** の場合は、既定値の代わりに **[ConversationsPerHour]** フィールドに指定した値が使用されます。
  
#### <a name="mobility-tab"></a>[Mobility] タブ

このタブを使用して、モビリティ関連のシナリオのすべてを構成します。
  
![Load Configuration Tool の [Mobility] タブ。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
次のオプションがあります。
  
- **General Mobility Settings**: **[Additional Settings]** をクリックして、[UcwaTargetServerUrl] フィールドをフロント エンド プール VIP のディレクトリ プール仮想 IP (VIP) に設定します。
    
- **Presence and P2P Instant Messaging/Audio**: 負荷レベルの値を選択して、モビリティのシミュレーションを有効にします。
    
> [!NOTE]
> それぞれのシナリオの横には **[Advanced]** ボタンが配置されています。 [Advanced] ダイアログには、Stress and Performance Tool の動作を変更してカスタマイズを可能にする、各シナリオに固有の値が含まれています。> それぞれの [Mobility] のシナリオについて、負荷レベルが **[Custom]** の場合は、既定値の代わりに **[ConversationsPerHour]** フィールドに指定した値が使用されます。
  
#### <a name="summary-tab"></a>[Summary] タブ

[Summary] タブには、シナリオごとに使用するユーザーが示されます。
  
![Load Configuration Tool の [Summary] タブ。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
[Summary] タブには、シナリオごとに使用するユーザーが示されます。 
  
ユーザー番号の範囲は、**[Enable Custom User Range Generation]** チェック ボックスをオンにして、表内でカスタマイズするユーザー範囲があるシナリオをダブルクリックすると手動で構成できます。
  
サインイン レートに合せて生成されたバッチ ファイルに遅延を含める場合は、**[(RunClient.bat) Add sign-in delay when starting]** をオンにします。 これは、多数のユーザーがサインにするときにサーバーの過負荷を防止する際に役立ちます。
  
**[Generate Files]** をクリックして、構成の生成先にするフォルダーを選択します。 ファイルが正常に作成されると、ダイアログ ボックスが表示されます。
  
!["Load configuration files generated successfully" というメッセージ ボックス。 そのまま [OK] をクリックします。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>LyncPerfTool の実行
<a name="BKMK_RunTool"> </a>

Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) の実行前に、ユーザー、連絡先、およびシナリオを作成する必要があります。 これらの操作を実行するツールの使用方法の詳細については、この記事で前述した「[ユーザーと連絡先の作成](using-the-tool.md#BKMK_CreateUsersAndContacts)」および「[ユーザー プロファイルの構成](using-the-tool.md#BKMK_UserProfile)」を参照してください。 これらのツールを実行することで、必須のパラメーターが含まれたバッチ ファイルの一部として、Stress and Performance Tool で実行するファイルも生成されます。
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool の実行

Load Configuration ツール (UserProfileGenerator.exe) では、パフォーマンス カウンターを登録して XML 構成ファイルを読み込むことで、Stress and Performance Tool (LyncPerfTool.exe) の実行が可能になるバッチ ファイルを作成します。 このバッチ ファイルでは、構成ファイルごとに LyncPerfTool.exe の 1 つのインスタンスを実行します。 バッチ ファイルを実行するには、次の手順を実行します。
  
### <a name="run-the-stress-and-performance-test"></a>Stress and Performance テストの実行

1. 各クライアント コンピューターの LyncPerfTool.exe があるディレクトリに、構成フォルダーとファイルが含まれているフォルダーをコピーします  (たとえば、1.28_13.16.16 という名前のフォルダー内に構成ファイルを生成した場合は、そのフォルダーを LyncPerfTool.exe が含まれているフォルダーにコピーします。 この操作をクライアントごとに実行します)。
    
2. クライアントのフォルダーに移動して、**RunClient** バッチ スクリプトを実行します。 Windows のエクスプローラーでバッチ ファイルをダブルクリックすると、そのクライアント用のすべての構成ファイルを実行できます。 また、次の構文を使用して、クライアントのフォルダーからスクリプトを実行することもできます。
    
   ```PowerShell
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Stress and Performance Tool を直接実行するには、コマンド プロンプトを開いて、コマンド ラインで次のコマンドを入力します (この操作を初めて実行する場合は、このトピックの注記で後述するように、パフォーマンス カウンターの登録 `regsvr32 /i /n /s LyncPerfToolPerf.dll` を実行してください)。
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

ツールで構成ファイル内の値が表示されるようにするには、次に示すように、前述のコマンドに `/displayfile` パラメーターを含めます。
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

処理を*終了*するには、Ctrl キーを押しながら C キーを押します。
  
> [!NOTE]
> Stress and Performance Tool を直接実行する前に、コマンド `regsvr32 /i /n /s LyncPerfToolPerf.dll` でパフォーマンス カウンターを登録する必要があります。
  
> [!NOTE]
> 起動した Stress and Performance Tool のすべてのインスタンスは、通常、1 秒間に 1 ユーザーの割合でユーザーのサインインをすぐに開始します。 
  
プールに対するユーザー サインインの最大レートは、毎秒約 12 ユーザーになります。 そのため、ユーザーがサインインしている間は、同時に 12 個よりも多くの LyncPerfTool.exe のインスタンスを実行しないでください。 1 秒間に 1 ユーザーの割合で 1000 ユーザーが完全にサインインするには、約 20 分かかります。
  
## <a name="interpreting-the-results"></a>結果の解釈
<a name="BKMK_Interpret"> </a>

Skype for Business Server 2015 Stress and Performance Tool には、クライアントの実行内容と問題が発生しているかどうかを判断する際に役立つ多くのカウンターがあります。
  
### <a name="client-counters"></a>クライアントのカウンター

実行中の LyncPerfTool.exe の各インスタンスには、カウンターの個別のインスタンスがあります。 それぞれのインスタンスには、そのプロセス ID による名前が付けられます。 クライアントが過負荷になると、別の問題が発生することがあります。 こうした問題を防止するには:
  
- クライアント コンピューターの CPU およびメモリの使用状況を監視します。 CPU が継続的に 90% 以上になっている場合は、ユーザーの数を減らします。
    
- メモリ占有領域が大きいときに、ページ ファイルが不足すると問題が発生することがあります。 コミット チャージがコンピューターの制限に達していないことを確認してください。 メモリ制限に達した場合は、ページ ファイルのサイズを大きくするか、ユーザーの数を減らします。
    
次に、主なパフォーマンス カウンターのリストを示します。
  
**一般情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Time Spent in Minutes  <br/> |プロセスの開始からの経過時間。  <br/> |
|Active Endpoints  <br/> |現在サーバーに接続しているエンドポイントの数。  <br/> |
|Failed Logons  <br/> |エンドポイント サインインの合計失敗数。  <br/> |
|Logon Attempts  <br/> |エンドポイント サインインの合計試行数。  <br/> |
|Endpoints Disconnected  <br/> |切断されたエンドポイントの合計数。  <br/> |
   
**プレゼンス情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|SetPresence Calls  <br/> |プレゼンス変更の合計試行数。 プレゼンス変更のさまざまな種類については、SetPresence (プレゼンスの種類) Calls パフォーマンス カウンターを参照してください。  <br/> |
|NNN Responses for SetPresence  <br/> |サーバーから受信した nnn 応答コードの合計数。  <br/> |
|GetPresence Calls  <br/> |プレゼンス取得要求の合計試行数。  <br/> |
|NNN Responses for GetPresence  <br/> |サーバーから受信した nnn 応答コードの合計数。  <br/> |
   
**アドレス帳サービスの情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |試行された完全または差分ファイル ダウンロード要求の合計数。  <br/> |
|ABS Full/Delta File Downloads Succeeded  <br/> |試行された完全または差分ファイル ダウンロード要求の合計数。  <br/> |
|アドレス帳 Web クエリ サービスに関連するカウンター  <br/> |アドレス帳ファイルのダウンロードに関連するカウンター。  <br/> |
|ABS WS Calls attempted  <br/> |試行したアドレス帳 Web クエリ サービス要求の合計数。  <br/> |
|ABS WS Calls Succeeded  <br/> |成功応答コードを返したアドレス帳 Web クエリ サービス要求の合計数。  <br/> |
|ABS WS Calls Failed  <br/> |エラー応答コードを返したアドレス帳 Web クエリ サービスの合計数。  <br/> |
   
> [!NOTE]
> このカテゴリには、アドレス帳サービス (ABS) のファイル ダウンロードとアドレス帳 Web クエリ サービスの要求を監視するために使用するカウンターが含まれています。 
  
**配布リスト (DL) の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Calls Attempted  <br/> |試行した配布リスト展開 (DLX) Web サービス要求の合計数。  <br/> |
|Calls Succeeded  <br/> |成功応答コードを返した DLX Web サービス要求の合計数。  <br/> |
|Calls Failed  <br/> |エラー応答コードを返した DLX Web サービス要求の合計数。  <br/> |
   

  
> [!NOTE]
> 次に示す各パフォーマンス カウンターは、すべての Voice over IP (VoIP) の通話数を報告します。これには、仲介サーバー、音声ビデオ会議サーバー、エッジ サーバー、応答グループ アプリケーション、および電話会議自動応答に対する通話が含まれます (これらのシナリオが有効な場合)。 
  
**VoIP の基本情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Calls Active  <br/> |現在進行中の着信/発信音声通話の合計数。  <br/> |
|Calls Terminated  <br/> |既に終了している着信/発信音声通話の合計数。  <br/> |
|Calls Declined  <br/> |拒否した着信音声通話の合計数。  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |試行した着信/発信音声通話の合計数。  <br/> |
|Incoming/Outgoing Calls Established  <br/> |成立した着信/発信音声通話の合計数。  <br/> |
|Calls Received NNN  <br/> |サーバーから受信した nnn 応答コードの合計数。  <br/> |
|VoIP Pass Rate (%)  <br/> |成立した通話の合計/試行した通話の合計。  <br/> |
   
**応答グループ サービス通話の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Calls Active  <br/> |応答グループ アプリケーションへのアクティブな通話の合計数。  <br/> |
|Calls Attempted  <br/> |試行した通話の合計数。  <br/> |
   
**インスタント メッセージング (IM) 通話の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Calls Active  <br/> |進行中の着信/発信インスタント メッセージング通話の合計数。  <br/> |
|Calls Terminated  <br/> |既に終了している着信/発信インスタント メッセージング通話の合計数。  <br/> |
|Calls Received NNN  <br/> |サーバーから受信した nnn 応答コードの合計数。  <br/> |
|IM Messages Received/Sent  <br/> |すべてのセッションで受信または送信したメッセージの合計数。  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |試行した着信/発信インスタント メッセージング通話の合計数。  <br/> |
|Incoming/Outgoing Calls Established  <br/> |成立した着信/発信インスタント メッセージ通話の合計数。  <br/> |
   
**アプリケーション共有通話の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Calls Active  <br/> |進行中の着信/発信アプリケーション共有通話の合計数。  <br/> |
|Calls Terminated  <br/> |既に終了している着信/発信アプリケーション共有通話の合計数。  <br/> |
|Calls Received NNN  <br/> |サーバーから受信した nnn 応答コードの合計数。  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |試行した着信/発信アプリケーション共有通話の合計数。  <br/> |
|Incoming/Outgoing Calls Established  <br/> |成立した着信/発信アプリケーション共有通話の合計数。  <br/> |
   
**CAA 通話の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Calls Active  <br/> |現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。  <br/> |
|Calls Terminated  <br/> |既に終了している着信/発信 PSTN 通話の合計数。  <br/> |
|Incoming/Outgoing Calls Attempted  <br/> |試行した着信/発信 PSTN 通話の合計数。  <br/> |
|Incoming/Outgoing Calls Established  <br/> |成立した着信/発信 PSTN 通話の合計数。  <br/> |
   
**会議通話の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Active Instant Messaging Conferences  <br/> |進行中のインスタント メッセージング会議通話の合計数。  <br/> |
|Active Audio/Video Conferences  <br/> |進行中の音声ビデオ (A/V) 会議通話の合計数。  <br/> |
|Active Application Sharing Conferences  <br/> |進行中のアプリケーション共有会議通話の合計数。  <br/> |
|Number of Participants  <br/> |会議通話に現在接続している参加者の合計数。  <br/> |
|Conference Schedule Failure  <br/> |会議通話のスケジュールに失敗した合計回数。  <br/> |
|Join Conference Failure  <br/> |会議通話への接続に失敗した合計回数。  <br/> |
   
**UCWA クライアントのカウンター**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|Total Number of IMMCU Joins Succeeded  <br/> |参加したインスタント メッセージング会議通話の合計数。  <br/> |
|Total Number of DMCU Joins Succeeded  <br/> |参加した音声ビデオ会議通話の合計数。  <br/> |
   

