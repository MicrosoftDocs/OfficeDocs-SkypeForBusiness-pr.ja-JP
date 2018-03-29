---
title: Using the Skype for Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
ms.openlocfilehash: 5f73ef6733c2f09cdf3e06bc8a6495c743d8b423
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Using the Skype for Business Server 2015 Stress and Performance Tool
 
To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
  
There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):
  
- [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configure User Profile](using-the-tool.md#BKMK_UserProfile)
    
- [Run LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpreting the Results](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Create Users and Contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.
  
This is a list of helpful terms that might be useful as you read through the topics:
  
- **Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).
    
- **Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.
    
- **Distribution Lists** - Or DLs. These are objects in AD DS that contain a list of AD DS users. They're used to facilitate communications across groups of people.
    
- **Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.
    
- **U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Create Users and Contacts by using UserProvisioningTool.exe

> [!NOTE]
> Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool. You need to do this, because you're going to be creating Active Directory users. 
  
You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.
  
The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package. Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.
  
You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.
  
> [!IMPORTANT]
> When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe. You'll need to do this because the tool will be creating and configuring  *new*  AD users.
  
When the User Provisioning Tool opens, click Configuration and select the Load Configuration. 
  
To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml". This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.
  
If you have a preconfigured XML file that already contains your customized settings, you can load that file instead. Fill in the fields in the User Provisioning Tool, as described in the sections below.
  
### <a name="to-configure-server-options"></a>To configure server options:

1. In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.
    
2. In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").
    
3. In the **Password** field, type a password that will be used across all the test user accounts.
    
4. In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).
    
5. In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users. (If the OU doesn't already exist, it'll be created for you).
    
6. In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts. Make certain that the area code you chose doesn't conflict with other users' area codes in AD.
    
7. Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.
    
8. In the **Number of Users** field, give the total number of test users you want to create.
    
9. In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)
    
     ![[User Creation] タブを表示している User Provisioning Tool](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>ユーザー ボタンを作成します。

When you click on the **Create Users** button, the input parameters you've entered are validated. If there are any validation errors, you'll be prompted to fix them. Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified). 実行時にツールの下部にある進行状況バーが表示されます。 Don't close the application while the progress bar is active.
  
User creation takes time, so please plan accordingly. This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.
  
If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create. Remember to use the prefix, and the suffix, along with the @sipDomain as the username. Here is an example:  *TestUser20@contoso.net*  .
  
> [!NOTE]
> If the users already exist, clicking the Create Users button will update them with any configuration changes. 
  
#### <a name="delete-users-button"></a>Delete Users button

When you click on the **Delete Users** button, the tab's input parameters will be validated. If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory. Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.
  
> [!NOTE]
> Only U.S.-formatted phone numbers are supported. Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default. Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls. For this reason,  *every user*  must have a *unique phone number*  .
  
> [!NOTE]
> **If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**
  
> [!IMPORTANT]
> Before you create contacts, you first need to complete user replication (which is done from the Users tab). 
  
> [!IMPORTANT]
> If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database. **ユーザーの複製が終了していない、エラーが表示されます。** You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.
  
#### <a name="contacts-creation-tab"></a>連絡先の作成] タブ

このタブでは、テストのユーザーの連絡先の詳細情報を提供することができます。
  
![[Contents Creation] タブを表示している User Provisioning Tool](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>ユーザーの連絡先を構成するには、次の操作を行います。

1. In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.
    
2. Select the **Fixed** check box if you want to create an equal number of contacts for every user. ユーザー用に作成された連絡先の数を変更する場合は、チェック ボックスをオフにします。
    
3. In the **Average Contact Groups per User** field, enter the number of contact groups per user. This number needs to be smaller than **Average Contacts per User**.
    
4. **連合/間のプール連絡先の割合**] フィールドに、0 から 100 までの数字を提供します。 フェデレーション ユーザーとの取引先担当者は、この割合が作成されます。
    
5. **連合/クロス プール ユーザー プレフィックス**] フィールドに、ローカル ユーザーの連絡先リストに追加されるフェデレーション ユーザーのユーザー名を提供します。
    
6. **連合/プール ユーザーの SIP ドメインを越える**フィールドに、フェデレーション ユーザーの SIP ドメイン名を提供します。
    
7. In **User Creation** tab make sure the information is correct. 連絡先は、ユーザーの作成] タブ上の値から作成されます。
    
8. 連絡先の作成を開始するのには**連絡先の作成**] をクリックします。 このプロセスには数分かかることができます。 それが完了した後、メッセージがダイアログ ボックスが表示されます「操作が完了正常にします。」 ユーザーの作成] タブから作成されたユーザーとしてログオンし、作成された連絡先を検証することができます。
    
> [!NOTE]
> 連絡先が作成されると、このツールは、ターゲット ・ プールのすべてのフロント エンド サーバーを再起動します。 によって顧客の数は、この操作によって作成された長い時間 (最大 2 時間) を開始するには、フロント エンド サーバーをかかることがあります。 
  
#### <a name="distribution-list"></a>配布リスト

ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype では、ビジネス 2015年クライアントの Skype での配布リスト (DL) の拡張機能をシミュレートできます。 ユーザー プロビジョニング ツールで、配布リストの展開を有効にしない場合は、この手順を省略できます。
  
![[Distribution List Creation] タブを表示している User Provisioning Tool](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
配布リスト] タブを使用すると、配布リストの展開機能のストレスおよびパフォーマンス ツールを使用する配布リストを作成できます。 配布リストを作成する前にビジネス サーバー 2015 の Skype が必要となる、ForestPrep を実行することを含みます。 、実行されていない場合、配布リストの属性は存在しません、AD スキーマのツールは、配布リストを作成するのにはできませんので。
  
### <a name="to-configure-distribution-lists"></a>配布リストを構成するには。

1. **配布リスト数**] フィールドに、作成する配布リストの合計数を指定します (ここでお勧めするユーザー数の 2 倍の値で開始すること。)。
    
2. **配布リストのプレフィックス**] フィールドに、作成するすべての配布リストがある、プレフィックス、 *testDL*などを入力します。 100 の Dl で、つまり、配布リスト名のようになります: testDL0、testDL1、testDL99 まで。
    
3. **版リストの最小のメンバー** ] フィールドに、各配布リストにユーザーの最小数を入力します。
    
4. **版リストの最大のメンバー** ] フィールドに、各配布リストに追加するユーザーの最大数を入力します。
    
#### <a name="create-distribution-lists-button"></a>配布リスト] ボタンを作成します。

配布リストの作成] ボタンをクリックするとツールは、配布リストをプリフィックスと番号が既に存在と一致するかどうかを確認するのには Active Directory を照会します。 ツールは、既に存在しないこれらの Dl を作成します。 メンバーを追加する配布リストを新しく作成された、ときに、ユーザーの作成] タブで指定された範囲からユーザーを選択にします。
  
#### <a name="location-info-service-config-tab"></a>場所情報サービスの構成] タブ

ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype では、場所情報サービスのダミーの構成ファイルを生成することも。 場所情報サービス通常はパフォーマンスに大きな影響であるサーバーに注意してください。 
  
![[Location Info Service Config] タブを表示している User Provisioning Tool](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
この機能をテストする場合は、フォーム内の値を入力し、LIS 構成ファイルの生成] ボタンをクリックを作成します。CSV ファイルと呼ばれます。
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
インポートするのには、LIS データベースにこれらのファイルは、次の PowerShell コマンドレットを使用します。
  
- セット CsLisSubnet
    
- セット CsLisSwitch
    
- セット CsLisPort
    
- セット CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>ユーザー プロファイルを構成します。
<a name="BKMK_UserProfile"> </a>

(ユーザー作成ツール) を使用して、ユーザーが作成された後は、ビジネス サーバー 2015 負荷構成ツール (UserProfileGenerator.exe) の Skype でユーザー プロファイルを構成できます。
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>ビジネス サーバー 2015 の読み込みの構成ツールの Skype を実行しています。

負荷の構成ツール (UserProfileGenerator.exe) を起動し、タブを入力します。 このツールは、シミュレーションを実行する必要があるコンピューター、クライアントごとにディレクトリを作成します。 各クライアントのディレクトリには、ビジネス サーバー 2015 のストレスおよびパフォーマンス ツール (LyncPerfTool.exe) は、Skype を起動するためのスクリプトが付属しています。 以下のセクションでは、ビジネス サーバー 2015 の読み込みの構成ツールの Skype の各タブのフィールドに入力する方法の例を提供します。
  
> [!IMPORTANT]
> 負荷の構成ツール (UserProfileGenerator.exe) で使用されるユーザー固有の値は、プールのビジネス サーバー 2015 ユーザー作成ツール (UserProvisioningTool.exe) は、Skype で指定した値に一致しなければなりません。 
  
#### <a name="common-configuration-tab"></a>Common Configuration tab

負荷の構成ツールの**一般的な設定**] タブを次に示します。 次の手順で説明したように、共通の設定] タブのフィールドを入力します。
  
![[Common Configuration] タブを表示している [User Provisioning] タブ](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. **使用可能なマシンの数**」フィールドには、ストレスおよびパフォーマンス ツール (LyncPerfTool.exe) の実行に使用するコンピューターの数を入力します。 シミュレートすることがあります、4500 のユーザーごとに 1 台のコンピューターがあるが、負荷のレベルを削減またはツールの使用可能な機能が (一般的なシナリオ] タブで設定されている負荷レベル) のサブセットのみを使用する場合、その番号は異なる場合がありますをお勧めします。
    
2. **ユーザー名のプレフィックス**] フィールドに、すべてのユーザーのユーザー名フィールドのプレフィックスを入力します。 統一リソース識別子 (URI) をログに記録されます: *UserPrefix [ユーザーの開始インデックス。(ユーザー 1 の数)]@User ドメイン*は、myUser009@Contoso.com です。
    
3. **すべてのユーザーのパスワード**フィールドに、ユーザーの作成時に使用するパスワードを入力します。 このフィールドを空のままにする場合は、パスワードとユーザー名が設定されます。
    
4. **ユーザー開始インデックス**フィールドで構成する最初のユーザーのインデックスを入力します。 さまざまな種類のレベルの負荷を複数の範囲を構成することができますが、範囲ごとに構成すると、読み込む構成ツール (UserProfileGenerator.exe) を実行する必要があります。
    
5. [**ユーザー数**] フィールドで構成しようとしているユーザーの合計数を入力します。
    
6. **ユーザー ドメイン**フィールドに、SIP URI に使用するドメインを入力します。 これは、ビジネス 2015 フロント エンド サーバーまたは Standard Edition サーバーでは、Skype にログオンする各ユーザーの SIP URI を構築するために使用し、アカウントのドメインと異なる場合があります。
    
7. [**アカウントのドメイン**] フィールドで、AD DS ドメインへのログオンを入力します。
    
8. In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.
    
9. **あたり 2 つ目 (インスタンス) ごとに署名**フィールドに、同時実行のエンドポイントの最大数を入力します。 これは、最大数は、ユーザーのログインし、1 秒あたり 2 と同じまたはそれより小さい数をお勧め (< = 2)。
    
10. [**アクセス プロキシまたはプールの FQDN** ] フィールドでは、クライアントに接続するサーバーの完全修飾ドメイン名 (FQDN) を入力します。 ユーザーがログオンに外部から、アクセス プロキシを入力する必要があります。 ユーザーが内部の場合は、エンタープライズ プールまたは Standard Edition サーバーの FQDN を提供します。
    
11. In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).
    
12. **外部のネットワーク サーバーの設定**のフィールドには、アクセス プロキシまたはプールの FQDN と、もう一度、**ポート**を提供します。 これらの設定は、外部エンドポイントの負荷のシミュレーションにのみ使用されます。
    
#### <a name="general-scenarios-tab"></a>General Scenarios tab

![[General Scenarios] タブを表示している Load Configuration Tool](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
実行するか、無効のままにする対象を決定することにより提供される一般的なシナリオのそれぞれについて、負荷のレベルとパラメーターを設定できます。 Here are your general options:
  
> [!NOTE]
> Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**. 無効になっているのですが、任意の設定を選択する場合は、構成をクライアントごとに生成されます。 High results in the max supported load on the server; medium is 60% of high load; low is 30%. 
  
- **インスタント メッセージングでは、**ピア ツー ピアおよび会議。負荷のレベルの適切な値を選択します。
    
- **Audio Conferencing -** Choose a load level for audio conferencing *only*  . Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section. マルチビューを有効にするのには [**詳細設定**] タブを開きます。
    
- **Application Sharing -** Choose a load level for application sharing.
    
- **Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.
    
- **配布リストの展開-****[詳細**] ボタンをクリックし、ユーザー作成ツール (UserProvisioningTool.exe) の [配布リスト] タブで構成されている同じ値を持つフィールドに入力します。 Choose a load level.
    
- **Address Book Web Query -** This is the address book lookup service rather than the address book file download. 場合は、[**詳細設定**] ボタンをクリックしてアドレス帳ファイルのダウンロードを有効にして、 **EnableABSDownload**を True に設定します。 Give a value for load level.
    
- **Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents. You must choose at least one response group. To use more, separate the response groups with semicolons. Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values. Choose a load level.
    
- **場所情報サービス-**有効または無効のいずれかの負荷レベルを選択します。
    
> [!NOTE]
> Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting. 
  
- Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.
    
- Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.
    
-  *External*  tells the tool to also simulate external users.
    
These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.
  
For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box. The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .
  
The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios. If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.
  
#### <a name="voice-scenarios-tab"></a>Voice Scenarios tab

This is the tab for configuration of all your voice-related scenarios.
  
![Load Configuration Tool の [Voice Scenarios] タブ](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
オプションは次のとおりです。
  
- **VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields. You'll also give a value for Load Level. If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.
    
- **UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button. Click **Add** under the Mediation Server and PSTN. Make sure you have a route configured for the area code.
    
    > [!TIP]
    > You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration. 
  
- **Conferencing Attendant -** Supply a value for Load Level. Any value other than Disabled will enable the **Telephone Number** field. Enter the phone number of the Auto Attendant you want to use. Click **Advanced** and give a value for the **LocationProfile** field.
    
- **Call Parking Service -** Here, supply a Load Level.
    
- **Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator. After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured. Click the **Add** button to configure a value for the Mediation Server.
    
    > [!NOTE]
    > Each scenario has an Advanced button located next to it. Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization. > For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box. The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .
  
#### <a name="web-app-tab"></a>Web App tab

![Load Configuration Tool の [Web app] タブ](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server. Use the Web App tab to configure all web app-related scenarios. Options are:
  
- **General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.
    
- **Application Sharing -** Select a value for Load Level.
    
- **データの共同作業-**負荷レベルの値を選択します。
    
- **インスタント メッセージングでは、**負荷レベルの値を選択します。
    
- **Voice Conferencing -** Select a value for Load Level.
    
> [!NOTE]
> Each of the scenarios has an **Advanced** button located next to it. Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.
  
#### <a name="mobility-tab"></a>モビリティ] タブ

すべてのモビリティに関連するシナリオを構成するのにには、このタブを使用します。
  
![Load Configuration Tool の [Mobility] タブ](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
オプションをここでは次のとおりです。
  
- **General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.
    
- **プレゼンスと P2P インスタント メッセージング/オーディオ-**移動のシミュレーションを有効にするのには負荷のレベルの値を選択します。
    
> [!NOTE]
> 各シナリオには、**詳細設定**] ボタンの横にあります。 Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.
  
#### <a name="summary-tab"></a>[概要] タブ

[概要] タブでは、各シナリオで使用するユーザーを示します。
  
![Load Configuration Tool の [Summary] タブ](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
The Summary tab indicates which users to use for each of the scenarios. 
  
It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.
  
サインインの速度に対応して生成されたバッチ ファイルでの遅延を含めるために**(RunClient.bat) 追加記号で遅延起動時の設定**を確認してください。 This is useful to prevent server overload when signing in a large number of users.
  
**ファイルの生成**] をクリックし、構成を生成するフォルダーを選択します。 ファイルが正常に作成されたときにダイアログ ボックスが表示されます。
  
!["Load configuration files generated successfully" というメッセージ ボックス。そのまま [OK] をクリックします。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>LyncPerfTool を実行します。
<a name="BKMK_RunTool"> </a>

You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe). For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article. Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Running the Skype for Business Server 2015 Stress and Performance tool

負荷の構成ツール (UserProfileGenerator.exe) は、ストレスおよびパフォーマンス ツール (LyncPerfTool.exe) を実行するには、パフォーマンス カウンターを登録して、XML 構成ファイルをロードすることを可能にするバッチ ファイルを作成します。 バッチ ファイルは、構成ファイルごとの LyncPerfTool.exe の 1 つのインスタンスを実行します。 バッチ ファイルを実行には、これらの手順に従います。
  
### <a name="run-the-stress-and-performance-test"></a>ストレスおよびパフォーマンスのテストを実行します。

1. Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer. (For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it. これは各クライアントにします。)
    
2. Navigate to the client folder and run the **RunClient** batch script. Windows エクスプ ローラーでバッチ ファイルをダブルクリックすることができ、すべての構成ファイルにクライアントに対して実行されます。 次の構文を使用してクライアントのフォルダーからスクリプトを実行することもできます。
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

ストレスおよびパフォーマンス ツールを直接実行、コマンド プロンプトを開き、コマンドラインで次のコマンドを入力する (最初にこれを行うときは、パフォーマンス カウンターを登録することを確認して`regsvr32 /i /n /s LyncPerfToolPerf.dll`、このトピックの後半で示すように、)。
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

*終了*処理をするには、Ctrl キーを押しながら C キーを押します。
  
> [!NOTE]
> ストレスおよびパフォーマンス ツールを直接実行する前に、次のコマンドを使用してパフォーマンス カウンターを登録する必要があります。`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> ストレスおよびパフォーマンス ツールを起動するすべてのインスタンスはすぐに 1 人のユーザーが 1 秒あたりの速度で通常のユーザーに署名します。 
  
レート プールのサインイン用ユーザーのピーク時は、1 秒あたり 12 についてです。 これは、必要はありませんを起動する 12 の複数の LyncPerfTool.exe インスタンスを同時にユーザーがサインインしても、ことを意味します。 1000 人のユーザーは完全に 1 秒ごとに 1 つのサインインに約 20 分かかります。
  
## <a name="interpreting-the-results"></a>Interpreting the Results
<a name="BKMK_Interpret"> </a>

ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype では、クライアントが何をして、には問題が発生したかどうかを理解するのに役立つ多数のカウンターがあります。
  
### <a name="client-counters"></a>クライアント カウンター

実行している LyncPerfTool.exe の各インスタンスには、別のカウンターのインスタンスがあります。 各インスタンスは、プロセス ID によってという名前 クライアントがオーバー ロードされた場合その他の問題が発生することができます。 これらの問題を防ぐ。
  
- クライアント コンピューター上の CPU とメモリの使用率を監視します。 CPU が継続的に、90% を超える場合は、ユーザーの数を減らします。
    
- メモリ使用量が高いときは、ページ ・ ファイル領域が不足する場合の問題に実行できます。 コミット チャージがコンピューター上の制限をヒットしないことを確認します。 メモリの制限に実行している場合は、ページ ファイル サイズを増やすか、ユーザーの数を減らすことを検討してください。
    
主要なパフォーマンス カウンターの一覧を以下に示します。
  
**一般的な情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|時間を分単位で  <br/> |プロセスが開始されたために費やされた時間。  <br/> |
|アクティブなエンドポイント  <br/> |サーバーに現在接続されているエンドポイントの数です。  <br/> |
|失敗したログオン  <br/> |サインインに失敗したエンドポイントの合計数です。  <br/> |
|ログオンの試行  <br/> |エンドポイント サインイン試行の合計数です。  <br/> |
|エンドポイントが切断されています。  <br/> |接続が切れたエンドポイントの合計数です。  <br/> |
   
**プレゼンス情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|SetPresence の呼び出し  <br/> |プレゼンスの合計数は、試行回数を変更します。 プレゼンス変更の種類は、SetPresence (プレゼンス型) の呼び出しのパフォーマンス カウンターを参照してください。  <br/> |
|SetPresence の NNN の応答  <br/> |Nnn 応答コードがサーバーからの受信の合計数です。  <br/> |
|GetPresence の呼び出し  <br/> |数の合計は、プレゼンス要求の回数を取得します。  <br/> |
|GetPresence の NNN の応答  <br/> |Nnn 応答コードがサーバーからの受信の合計数です。  <br/> |
   
**アドレス帳サービスの情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|ABS フル/差分ファイルをダウンロードしようとしました  <br/> |フルまたは差分ファイルのダウンロード要求が試行の合計数です。  <br/> |
|ABS フル/差分ファイルのダウンロードに成功しました  <br/> |フルまたは差分ファイルのダウンロード要求が試行の合計数です。  <br/> |
|アドレス帳 Web クエリ サービスに関連するカウンター  <br/> |アドレス帳ファイルは、関連するカウンターをダウンロードします。  <br/> |
|ABS WS 呼び出しを実行しようと  <br/> |実行しようとアドレス帳 Web クエリ サービスの要求の合計数です。  <br/> |
|ABS WS の呼び出しに成功しました  <br/> |正常な応答コードが返されるアドレス帳 Web クエリ サービスの要求の合計数です。  <br/> |
|ABS WS の呼び出しに失敗しました。  <br/> |エラー応答コードが返されるアドレス帳 Web クエリ サービスの要求の合計数です。  <br/> |
   
> [!NOTE]
> このカテゴリには、アドレス帳サービス (ABS) ファイルをダウンロードし、アドレス帳 Web クエリ サービス要求を監視するために使用するカウンターが含まれています。 
  
**配布リスト (DL) の情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|呼び出しを実行しようと  <br/> |配布リストの拡張されて web サービス要求が試行の合計数です。  <br/> |
|呼び出しに成功しました  <br/> |正常な応答コードが返されましたが、DLX の web サービス要求の合計数です。  <br/> |
|呼び出しが失敗しました。  <br/> |エラー応答コードが返された DLX の web サービス要求の合計数です。  <br/> |
   

  
> [!NOTE]
> パフォーマンス カウンターを以下に示しますレポート番号のボイスはすべての IP (VoIP) 呼び出しは、仲介サーバー、A への呼び出しなどの上/V 会議サーバー、エッジ サーバー、応答グループ アプリケーション、および会議の自動応答、これらのシナリオを有効にします。 
  
**VoIP の基本情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|アクティブな呼び出し  <br/> |音声の着信/発信の合計数は現在進行中呼び出されます。  <br/> |
|呼び出しが終了しました  <br/> |音声通話の着信/発信の合計数は既に終了しました。  <br/> |
|呼び出しが拒否されました。  <br/> |着信音声通話の合計数を辞退しました。  <br/> |
|着信/発信呼び出しを実行しようと  <br/> |着信/発信音声呼び出しを試行の合計数です。  <br/> |
|着信/発信呼び出しの確立  <br/> |確立された着信/発信音声通話の合計数です。  <br/> |
|呼び出しの受信した NNN  <br/> |Nnn 応答コードがサーバーからの受信の合計数です。  <br/> |
|VoIP の成功率 (%)  <br/> |合計通話が確立されると合計実行しようとします。  <br/> |
   
**応答グループ サービスの呼び出しについて**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|アクティブな呼び出し  <br/> |応答グループ アプリケーションのアクティブな呼び出しの合計数です。  <br/> |
|呼び出しを実行しようと  <br/> |実行しようとする呼び出しの合計数です。  <br/> |
   
**インスタント メッセージング (IM) の呼び出しについて**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|アクティブな呼び出し  <br/> |継続的な着信/発信のインスタント メッセージング呼び出しの合計数です。  <br/> |
|呼び出しが終了しました  <br/> |インスタント メッセージング呼び出しの着信/発信の合計数は既に終了しました。  <br/> |
|呼び出しの受信した NNN  <br/> |Nnn 応答コードがサーバーからの受信の合計数です。  <br/> |
|受信/送信された IM メッセージ  <br/> |メッセージの合計数の受信または送信のすべてのセッションです。  <br/> |
|着信/発信呼び出しを実行しようと  <br/> |着信/発信インスタント メッセージングの呼び出しの試行の合計数です。  <br/> |
|着信/発信呼び出しの確立  <br/> |確立された着信/発信のインスタント メッセージ呼び出しの合計数です。  <br/> |
   
**アプリケーション呼び出し情報の共有**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|アクティブな呼び出し  <br/> |進行中の着信/発信アプリケーションの共有の呼び出しの合計数です。  <br/> |
|呼び出しが終了しました  <br/> |着信/発信のアプリケーションの呼び出しを既に共有の合計数が終了しました。  <br/> |
|呼び出しの受信した NNN  <br/> |Nnn 応答コードがサーバーからの受信の合計数です。  <br/> |
|着信/発信呼び出しを実行しようと  <br/> |着信/発信アプリケーションの共有しようとする呼び出しの合計数です。  <br/> |
|着信/発信呼び出しの確立  <br/> |着信/発信アプリケーションの共有を確立する呼び出しの合計数です。  <br/> |
   
**CAA の呼び出しについて**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|アクティブな呼び出し  <br/> |公衆交換電話網 (PSTN) の着信/発信の合計数は現在進行中呼び出されます。  <br/> |
|呼び出しが終了しました  <br/> |PSTN 通話の着信/発信の合計数は既に終了しました。  <br/> |
|着信/発信呼び出しを実行しようと  <br/> |PSTN 通話を受信/送信試行の合計数です。  <br/> |
|着信/発信呼び出しの確立  <br/> |確立された着信/発信の PSTN 通話の合計数です。  <br/> |
   
**会議情報**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|アクティブなインスタント メッセージング会議  <br/> |インスタント メッセージング会議を進行中の合計数です。  <br/> |
|アクティブなオーディオ/ビデオ会議  <br/> |数の継続的なオーディオ/ビデオ (A/V) 会議。  <br/> |
|アクティブなアプリケーションの共有の会議  <br/> |会議を共有して継続的なアプリケーションの合計数です。  <br/> |
|参加者の数  <br/> |会議に現在接続している参加者の合計数です。  <br/> |
|会議スケジュールの障害  <br/> |会議をスケジュールしようとしているときにエラーの合計数です。  <br/> |
|障害の会議に参加します。  <br/> |会議への接続中のエラーの合計数です。  <br/> |
   
**UCWA クライアント カウンター**

|**パフォーマンス カウンター**|**説明**|
|:-----|:-----|
|IMMCU の合計数を結合に成功しました  <br/> |インスタント メッセージング会議の合計数が参加しています。  <br/> |
|DMCU の合計数を結合に成功しました  <br/> |A の合計数 V 会議に参加するいるとします。  <br/> |
   

