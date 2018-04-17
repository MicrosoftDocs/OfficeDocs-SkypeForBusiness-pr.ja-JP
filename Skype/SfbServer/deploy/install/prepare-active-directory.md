---
title: Skype for Business Server 2015 用の Active Directory の準備
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Summary: Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 用の Active Directory の準備
 
**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server works closely with Active Directory. You must prepare the Active Directory domain to work with Skype for Business Server. このプロセスは展開ウィザードで行われ、ドメインに対して 1 回だけ実行されます。 これは、プロセスではグループを作成してドメインを変更しますが、その処理は 1 回だけ必要であるためです。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 Active Directory の準備は、8 つの手順の 4 番目です。 For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory の準備

Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS). Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared. The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology. Every server must be joined to the domain so that Skype for Business Server can work properly. 
  
> [!IMPORTANT]
> "Active Directory の準備" の手順は、展開のドメインごとに 1 回だけ実行する必要があります。 
  
**Active Directory の準備**手順に関するビデオをご覧ください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>展開ウィザードからの Active Directory の準備

1. Active Directory ドメインの Schema Admins の資格情報を持つユーザーとしてログオンします。
    
2. Open Skype for Business Server Deployment Wizard.
    
    > [!TIP]
    > If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step. For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. [**Active Directory の準備**] リンクをクリックします。
    
4. **Step 1: Prepare schema**
    
    a. 手順 1 の前提条件を確認します。"手順 1" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。
    
    b. 手順 1 の [**実行**] をクリックして、スキーマの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. スキーマが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    e. [**完了**] をクリックしてスキーマの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
5. **Step 2: Verify replication of schema partition**
    
    a. ドメインのドメイン コントローラーにログオンします。
    
    b. [**サーバー マネージャー**] の [**ツール**] ドロップダウン メニューから [**ADSI エディター**] を開きます。
    
    c. [**アクション**] メニューで、[**接続**] をクリックします。
    
    d. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
    e. スキーマ コンテナーで、**CN=ms-RTC-SIP-SchemaVersion** を検索します。 このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。 このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。
    
6. **Step 3: Prepare current forest**
    
    a. 手順 3 の前提条件を確認します。"手順 3" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。
    
    b. 手順 3 の [**実行**] をクリックして、現在のフォレストの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ユニバーサル グループを作成するドメインを指定します。 サーバーがドメインの一部である場合は、[**ローカル ドメイン**] を選択して、[**次へ**] をクリックします。
    
    e. フォレストが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    f. [**完了**] をクリックして現在のフォレストの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
    g. Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    h. Type the command Get-CsAdForest, and press **Enter**.
    
    i. If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.
    
     ![フォレスト レプリケーションの確認](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Step 4: Verify replication of the global catalog**
    
    a. フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。
    
    b. [**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。
    
    c. 左側のウィンドウの [**ユーザー**] コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を見つけます。 (先頭に Cs が付いた他の新しいユニバーサル グループと共に) CsAdministrator が表示されている場合、Active Directory のレプリケーションは成功しています。
    
    d. グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。 グループが表示されている場合、レプリケーションは完了しています。
    
8. **Step 5: Prepare the current domain**
    
    a. 手順 5 の前提条件の情報を確認します。
    
    b. 手順 5 の [**実行**] をクリックして、現在のドメインの準備ウィザードを起動します。
    
    c. 手順は、展開のドメインごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ドメインが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    e. [**完了**] をクリックして現在のドメインの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
    These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start. オブジェクトには、ユーザー、連絡先オブジェクト、管理グループなどのすべての種類の Active Directory オブジェクトや、他のすべての種類のオブジェクトが含まれます。 You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.
    
9. **Step 6: Verify replication in the domain**
    
    a. Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    b. Use the command Get-CsAdDomain to verify replication within the domain.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 
  
    contoso.local ドメインのコマンドの実行例:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する AD DS フォレストのルートに 1 つのドメイン コントローラーを定義します。グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。 
  
    c. If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.
    
10. **Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**
    
    a. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    b. [**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーをクリックし、CSAdministrator を右クリックして、[**プロパティ**] を選択します。
    
    c. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
    d. [**メンバー**] タブで [**追加**] をクリックします。 [**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。 CSAdministrators グループに追加するユーザー名またはグループ名を入力します。 [**OK**] をクリックします。
    
    e. [**メンバー**] タブで、選択したユーザーまたはグループが表示されていることを確認します。 [**OK**] をクリックします。
    
    > [!CAUTION]
    > The Skype for Business Server Control Panel is a role-based access control tool. Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available. 特定の機能向けに設計されたその他の役割も使用できます。 For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups. 
  
    > [!CAUTION]
    > To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment. 
  
11. Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.
    
12. 図のように、[**Active Directory の準備**] の横に成功を示す緑色のチェックマークが表示されていることを確認します。
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

