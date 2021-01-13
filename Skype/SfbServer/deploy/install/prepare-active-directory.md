---
title: Skype for Business Server 用の Active Directory の準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '概要: Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801677"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Skype for Business Server 用の Active Directory の準備
 
**概要:** Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版 [をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
Skype for Business Server は Active Directory と密接に関連して動作します。 Skype for Business Server を使用するには、Active Directory ドメインを準備する必要があります。 このプロセスは展開ウィザードで実行され、ドメインに対して 1 回だけ実行されます。 これは、プロセスによってグループが作成され、ドメインが変更され、1 回だけ行う必要があるためです。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 を順番に実行し、図に示されている手順 1 ~ 5 の後に実行する必要があります。 Active Directory の準備は、手順 4/8 です。 Active Directory の計画の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory の準備

Skype for Business Server は、Active Directory ドメイン サービス (AD DS) と緊密に統合されています。 Skype for Business Server を初めてインストールする前に、Active Directory を準備する必要があります。 「Active **Directory** の準備」というタイトルの展開ウィザードのセクションでは、Skype for Business Server で使用する Active Directory 環境を準備します。
  
> [!NOTE]
> Skype for Business Server は(AD DS) を使用して、トポロジ内のすべてのサーバーを追跡および通信します。 これらのサーバーの大部分は、Skype for Business Server が正常に動作するためにドメインに参加している必要があります。 エッジ やリバース プロキシなどのサーバーはドメインに参加しなけれな点に気を付ける必要があります。
  
> [!IMPORTANT]
> Active Directory の準備手順は、展開内のドメインごとに 1 回だけ実行してください。 
  
Active Directory の準備に関するビデオ **の手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>展開ウィザードから Active Directory を準備する

1. Active Directory ドメインの Schema Admins 資格情報を持つユーザーとしてログオンします。
    
2. Skype for Business Server 展開ウィザードを開きます。
    
    > [!TIP]
    > Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する場合は、展開ウィザードが実行されたコンピューターの手順を実行した AD DS ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。 たとえば、ユーザーがドメイン contoso.local でドメイン管理者としてログオンした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  
3. [Active **Directory の準備] リンクをクリック** します。
    
4. **手順 1: スキーマを準備する**
    
    a.  手順 1 のタイトルの下のドロップダウンをクリックしてアクセスできる手順 1 の前提条件情報を確認します。
    
    b. 手順 **1** で [実行] をクリックして、スキーマの準備ウィザードを起動します。
    
    c. この手順は展開ごとに 1 回だけ実行し、[次へ] **をクリックします**。
    
    d.  スキーマの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。 
    
    e.  [ **完了]** をクリックしてスキーマの準備ウィザードを閉じ、Active Directory の準備の手順に戻ります。
    
5. **手順 2: スキーマ パーティションのレプリケーションを確認する**
    
    a.  ドメインのドメイン コントローラーにログオンします。
    
    b. サーバー **マネージャーの [ツール]****ドロップダウン** メニューから ADSI Edit を **開きます**。
    
    c. **[アクション]** メニューで、**[接続]** をクリックします。
    
    d.  **[接続の設定]** ダイアログ ボックスの **[既知の名前付けコンテキストを選択する]** で、**[スキーマ]** を選択して **[OK]** をクリックします。
    
    e.  スキーマ コンテナーで **、CN=ms-RTC-SIP-SchemaVersion を検索します**。 このオブジェクトが存在し **、rangeUpper** 属性の値が 1150 で **rangeLower** 属性の値が 3 の場合、スキーマは正常に更新され、レプリケートされました。 このオブジェクトが存在しない場合、または **rangeUpper** 属性と **rangeLower** 属性の値が指定されていない場合、スキーマは変更されていないか、レプリケートされていません。
    
6. **手順 3: 現在のフォレストを準備する**
    
    a.  手順 3 の前提条件に関する情報を確認します。この情報には、手順 3 のタイトルの下にあるドロップダウンをクリックしてアクセスできます。
    
    b. 手順 **3** で [実行] をクリックして、現在のフォレストの準備ウィザードを起動します。
    
    c. この手順は展開ごとに 1 回だけ実行し、[次へ] **をクリックします**。
    
    d.  ユニバーサル グループを作成するドメインを指定します。 サーバーがドメインの一部である場合は、[ローカルドメイン] を選択し、[次へ] をクリック **します**。
    
    e.  フォレストの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。 
    
    f. [ **完了]** をクリックして現在のフォレストの準備ウィザードを閉じ、Active Directory の準備の手順に戻ります。
    
    g.  [**アプリ] ページから [Skype for Business Server 管理シェル**] をクリックして、PowerShell を起動します。 
    
    h. Get-CsAdForest コマンドを入力し **、Enter** キーを押します。
    
    i. 結果が **LC_FORESTSETTINGS_STATE_READY、次** の図に示すように、フォレストが正常に準備されています。
    
     ![フォレストのレプリケーションを確認します。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **手順 4: グローバル カタログのレプリケーションを確認する**
    
    a.  ドメイン コントローラー (他のドメイン コントローラーからのリモート サイトが望ましい) で、フォレストの準備が実行されたフォレストで、Active Directory ユーザーとコンピューター **を開きます**。
    
    b. **[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。
    
    c. 左側の **ウィンドウで Users** コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を探します。 CsAdministrator (Cs で始まる他の新しいユニバーサル グループ) が存在する場合、Active Directory のレプリケーションは成功しています。
    
    d.  グループがまだ存在しない場合は、レプリケーションを強制するか、15 分待って右側のウィンドウを更新します。 グループが表示されている場合、レプリケーションは完了しています。
    
8. **手順 5: 現在のドメインを準備する**
    
    a.  手順 5 の前提条件の情報を確認します。
    
    b. 手順 5 で [実行] をクリックして、現在のドメインの準備ウィザードを起動します。
    
    c. この手順は、展開内のドメインごとに 1 回だけ実行し、[次へ] **をクリックします**。
    
    d.  ドメインの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。 
    
    e.  [ **完了]** をクリックして現在のドメインの準備ウィザードを閉じ、Active Directory の準備の手順に戻ります。
    
    これらの手順は、Skype for Business Server オブジェクトが見つかったすべてのドメインで実行する必要があります。そうしないと、サービスが開始されない可能性があります。 これには、ユーザー、連絡先オブジェクト、管理グループ、その他の種類のオブジェクトなど、任意の種類の Active Directory オブジェクトが含まれます。 必要に応Set-CsUserReplicatorConfiguration -ADDomainNamingContextList を使用して、Skype for Business Server オブジェクトを持つドメインのみを追加できます。
    
9. **手順 6: ドメイン内のレプリケーションを確認する**
    
    a.  [アプリ **] ページから Skype for Business Server 管理シェル** をクリックして、PowerShell を起動します。
    
    b. コマンド プロンプトを使用Get-CsAdDomainドメイン内のレプリケーションを確認します。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 
  
    contoso.local ドメインのコマンドを実行する例:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用すると、グローバル設定を格納する場所を指定できます。 設定がシステム コンテナーに格納されている場合 (グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、AD DS フォレストのルートにドメイン コントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは設定が構成コンテナーに格納され、Active Directory 内の任意のドメイン コントローラーを参照すると想定します。 
  
    c. 結果が正しくレプリケート **LC_DOMAINSETTINGS_STATE_READY** ドメインは正常にレプリケートされています。
    
10. **手順 7: Skype for Business Server コントロール パネルへの管理アクセスを提供するユーザーを追加する**
    
    a.  Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    b. **Active Directory ユーザー** とコンピューターを開き、ドメインを展開し **、Users** コンテナーをクリックして、CSAdministrator を右クリックして、[プロパティ] を選択 **します**。
    
    c. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
    d.  [ **メンバー**] タブで [ **追加**] をクリックします。 [**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。 CSAdministrators グループに追加するユーザー名またはグループ名を入力します。 **[OK]** をクリックします。
    
    e.  [ **メンバー]** タブで、選択したユーザーまたはグループが存在する必要があります。 [**OK**] をクリックします。
    
    > [!CAUTION]
    > Skype for Business Server コントロール パネルは、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップにより、Skype for Business Server コントロール パネルを使用しているユーザーは、使用可能なすべての構成機能を完全に制御できます。 特定の機能向けに設計されたその他の役割も使用できます。 使用可能な役割の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 ユーザーを管理グループのメンバーにするために、Skype for Business Server を有効にする必要は必ずしもない点に注意してください。 
  
    > [!CAUTION]
    > セキュリティと役割ベースのアクセス制御の整合性を維持するために、Skype for Business Server 展開の管理でユーザーが実行する役割を定義するグループにユーザーを追加します。 
  
11. 新しい Skype for Business Server セキュリティ グループを使用してセキュリティ トークンが更新された後、展開ウィザードを再度開きます。
    
12. 図に示すように **、[Active Directory** の準備] の横に緑色のチェックマークが表示され、成功を確認します。
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>関連項目
 
[Skype for Business Server 2015 の Active Directory ドメイン サービス](../../plan-your-deployment/security/active-directory-domain-services.md)
