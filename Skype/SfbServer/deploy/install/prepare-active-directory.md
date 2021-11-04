---
title: 'Skype for Business Server: Active Directory の準備'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '概要: Active Directory ドメインをインストール用に準備する方法についてSkype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 882a57aa5ee857b0a4c633b6365c7a89c6266669
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775757"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>Skype for Business Server: Active Directory の準備
 
**概要:** Active Directory ドメインをインストール用に準備する方法についてSkype for Business Server。 Microsoft 評価センターからSkype for Business Server試用版[をダウンロードします](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
Skype for Business Server Active Directory と密接に動作します。 Active Directory ドメインを準備して、このドメインをSkype for Business Server。 このプロセスは展開ウィザードで実行され、ドメインに対して 1 回だけ実行されます。 これは、プロセスによってグループが作成され、ドメインが変更され、1 回だけ行う必要があるためです。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示されている手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 Active Directory の準備は、手順 4 / 8 です。 Active Directory の計画の詳細については、「環境要件 for [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) [2019」](../../../SfBServer2019/plan/system-requirements.md)を参照Skype for Business Serverしてください。
  
![概要図。](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory の準備

Skype for Business Server Active Directory ドメイン サービス (DS) と緊密にADされています。 インストールSkype for Business Serverする前に、Active Directory を準備する必要があります。 「Active Directory の準備」というタイトルの展開ウィザードのセクションでは、Active **Directory** 環境を準備して、この環境で使用Skype for Business Server。
  
> [!NOTE]
> Skype for Business Server (AD DS) を使用して、トポロジ内のすべてのサーバーを追跡および通信します。 これらのサーバーの大部分は、ドメインに参加して、サーバーが正常にSkype for Business Serverする必要があります。 エッジプロキシやリバース プロキシなどのサーバーはドメインに参加しなけれという点に気を付ける必要があります。
  
> [!IMPORTANT]
> [Active Directory の準備] プロシージャは、展開内のドメインごとに 1 回だけ実行する必要があります。 
  
「Active Directory の準備」のビデオ **手順をご覧ください**。
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>展開ウィザードから Active Directory を準備する

1. Active Directory ドメインのスキーマ管理者資格情報を持つユーザーとしてログオンします。
    
2. 展開ウィザードSkype for Business Server開きます。
    
    > [!TIP]
    > Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する場合は、展開ウィザードが実行されたコンピューターで、手順を実行した AD DS ユーザーの Users ディレクトリにあります。 たとえば、ユーザーがドメイン contoso.local のドメイン管理者としてログオンした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  
3. [Active **Directory の準備] リンクを** クリックします。
    
4. **手順 1: スキーマの準備**
    
    a. 手順 1 のタイトルの下にあるドロップダウンをクリックして、アクセスできる手順 1 の前提条件情報を確認します。
    
    b. 手順 **1 で** [実行] をクリックして、スキーマの準備ウィザードを起動します。
    
    c. 手順は展開ごとに 1 回だけ実行し、[次へ] をクリックする必要 **があります。**
    
    d. スキーマを準備したら、[ログの表示] をクリックしてログ **を表示できます**。 
    
    e. [ **完了]** をクリックしてスキーマの準備ウィザードを閉じ、[Active Directory の準備] 手順に戻ります。
    
5. **手順 2: スキーマ パーティションのレプリケーションを確認する**
    
    a. ドメインのドメイン コントローラーにログオンします。
    
    b. サーバー **マネージャーの [ツール]** **ドロップダウン メニュー** から [ADSI 編集] **を開きます**。
    
    c. **[アクション]** メニューで、**[接続]** をクリックします。
    
    d. **[接続の設定]** ダイアログ ボックスの **[既知の名前付けコンテキストを選択する]** で、**[スキーマ]** を選択して **[OK]** をクリックします。
    
    e. スキーマ コンテナーの下で **、CN=ms-RTC-SIP-SchemaVersion を検索します**。 このオブジェクトが存在し **、rangeUpper** 属性の値が 1150 で **、rangeLower** 属性の値が 3 の場合、スキーマは正常に更新され、レプリケートされました。 このオブジェクトが存在しない場合、または **rangeUpper** 属性と **rangeLower** 属性の値が指定されていない場合、スキーマは変更されていないか、レプリケートされていません。
    
6. **手順 3: 現在のフォレストを準備する**
    
    a. 手順 3 のタイトルの下にあるドロップダウンをクリックして、アクセスできる手順 3 の前提条件情報を確認します。
    
    b. 手順 **3 で** [実行] をクリックして、[現在のフォレストの準備] ウィザードを起動します。
    
    c. 手順は展開ごとに 1 回だけ実行し、[次へ] をクリックする必要 **があります。**
    
    d. ユニバーサル グループを作成するドメインを指定します。 サーバーがドメインの一部である場合は、[ローカルドメイン] を選択し、[次へ] をクリック **します**。
    
    e. フォレストの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。 
    
    f. [ **完了]** をクリックして現在のフォレストの準備ウィザードを閉じ、[Active Directory の準備] 手順に戻ります。
    
    g. [**アプリSkype for Business Server管理シェル]** をクリック **して** PowerShell を起動します。
    
    h. Get-CsAdForest コマンドを入力し、Enter キーを **押します**。
    
    i. 結果 **がLC_FORESTSETTINGS_STATE_READY、** 図に示すように、フォレストが正常に準備されました。
    
     ![フォレストのレプリケーションを確認します。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **手順 4: グローバル カタログのレプリケーションを確認する**
    
    a. ドメイン コントローラー (できれば、他のドメイン コントローラーからのリモート サイト) で、フォレスト準備が実行されたフォレストで **、Active Directory Users** and Computers を開きます。
    
    b. **[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。
    
    c. 左側の **ウィンドウで [Users]** コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を探します。 CsAdministrator (Cs で始まる他の新しいユニバーサル グループの中で) が存在する場合、Active Directory レプリケーションは成功しています。
    
    d. グループがまだ存在しない場合は、レプリケーションを強制するか、15 分待って右側のウィンドウを更新できます。 グループが表示されている場合、レプリケーションは完了しています。
    
8. **手順 5: 現在のドメインを準備する**
    
    a. 手順 5 の前提条件情報を確認します。
    
    b. 手順 **5** で [実行] をクリックして、[現在のドメインの準備] ウィザードを起動します。
    
    c. この手順は、展開内のドメインごとに 1 回だけ実行し、[次へ] **をクリックする** 必要があります。
    
    d. ドメインの準備が完了したら、[ログの表示] をクリックしてログ **を表示できます**。 
    
    e. [ **完了]** をクリックして現在のドメインの準備ウィザードを閉じ、[Active Directory の準備] 手順に戻ります。
    
    これらの手順は、オブジェクトが見つかったすべてのSkype for Business Server完了する必要があります。それ以外の場合は、サービスが開始されない可能性があります。 これには、ユーザー、連絡先オブジェクト、管理グループ、その他の種類のオブジェクトなど、任意の種類の Active Directory オブジェクトが含まれます。 必要に応じて、Set-CsUserReplicatorConfiguration -ADDomainNamingContextList を使用して、Skype for Business Serverオブジェクトを持つドメインのみを追加できます。
    
9. **手順 6: ドメイン内のレプリケーションを確認する**
    
    a. [アプリ]**ページSkype for Business Server管理シェル** をクリック **して**、PowerShell を起動します。
    
    b. ドメイン内のレプリケーションGet-CsAdDomainを確認するには、次のコマンドを使用します。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 
  
    contoso.local ドメインのコマンドを実行する例を次に示します。
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > GlobalSettingsDomainController パラメーターを使用すると、グローバル設定の格納場所を指定できます。 設定が System コンテナーに格納されている場合 (グローバル設定が構成コンテナーに移行されていないアップグレード展開では一般的です)、AD DS フォレストのルートにドメイン コントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは設定が構成コンテナーに格納され、Active Directory の任意のドメイン コントローラーを参照すると想定します。 
  
    c. 結果が **LC_DOMAINSETTINGS_STATE_READY、ドメイン** は正常にレプリケートされました。
    
10. **手順 7: ユーザーを追加して、コントロール パネルへのSkype for Business Serverを提供する**
    
    a. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    b. **[Active Directory ユーザーとコンピューター]** を開き、ドメインを展開し、[**ユーザー** ] コンテナーをクリックし、[CSAdministrator] を右クリックして、[プロパティ] を **選択します**。
    
    c. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
    d. [ **メンバー**] タブで [ **追加**] をクリックします。 [**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。 CSAdministrators グループに追加するユーザー名またはグループ名を入力します。 **[OK]** をクリックします。
    
    e. [メンバー **] タブ** で、選択したユーザーまたはグループが存在します。 [**OK**] をクリックします。
    
    > [!CAUTION]
    > [Skype for Business Serverコントロール パネル] は、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップを使用すると、使用可能なすべての構成機能にSkype for Business Serverコントロール パネルのフル コントロールを使用しているユーザーが表示されます。 特定の機能向けに設計されたその他の役割も使用できます。 使用可能なロールの詳細については、「環境[](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)要件」または「Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md)のサーバー要件」を参照Skype for Business Serverしてください。 管理グループのメンバーを作成するには、ユーザー Skype for Business Serverを有効にする必要はなんらない点に注意してください。 
  
    > [!CAUTION]
    > セキュリティと役割ベースのアクセス制御の整合性を維持するために、ユーザーが展開の管理で実行する役割を定義するグループにユーザーをSkype for Business Serverします。 
  
11. ログオフし、Windows にログオンし、セキュリティ トークンが新しい Skype for Business Server セキュリティ グループで更新された後、展開ウィザードを再度開きます。
    
12. 図に示すように、[Active **Directory** の準備] の横に緑色のチェックマークが表示され、成功を確認します。
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>関連項目
 
[Active Directory ドメイン サービス for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
