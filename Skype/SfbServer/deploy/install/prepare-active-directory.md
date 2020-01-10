---
title: Skype for Business Server 用 Active Directory の準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '概要: Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について説明します。 Skype for Business Server の無料トライアルは、次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターからダウンロードしてください。'
ms.openlocfilehash: 114b2a91491dd440972f589ff45d86835c676bef
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000887"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Skype for Business Server 用 Active Directory の準備
 
**概要:** Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について説明します。 [Microsoft の評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から Skype For business Server の無料トライアルをダウンロードします。
  
Skype for Business Server は Active Directory と密接に連携しています。 Skype for Business Server を使用するには、Active Directory ドメインを準備する必要があります。 このプロセスは展開ウィザードで行われ、ドメインに対して 1 回だけ実行されます。 これは、プロセスではグループを作成してドメインを変更しますが、その処理は 1 回だけ必要であるためです。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 Active Directory の準備は、8 つの手順の 4 番目です。 Active Directory の計画について詳しくは、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」をご覧ください。
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory の準備

Skype for Business Server は、Active Directory ドメインサービス (AD DS) と密接に統合されています。 Skype for Business Server を初めてインストールするには、Active Directory を準備しておく必要があります。 [ **Active directory の準備**] というタイトルの展開ウィザードのセクションでは、Skype For business Server で使用する active directory 環境を準備します。
  
> [!NOTE]
> Skype for Business Server は (AD DS) を使って、トポロジ内のすべてのサーバーを追跡し、通信します。 Skype for Business Server が正常に動作するためには、すべてのサーバーがドメインに参加している必要があります。 
  
> [!IMPORTANT]
> "Active Directory の準備" の手順は、展開のドメインごとに 1 回だけ実行する必要があります。 
  
**Active Directory の準備**手順に関するビデオをご覧ください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>展開ウィザードからの Active Directory の準備

1. Active Directory ドメインの Schema Admins の資格情報を持つユーザーとしてログオンします。
    
2. Skype for Business Server 展開ウィザードを開きます。
    
    > [!TIP]
    > Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した AD DS ユーザーの Users ディレクトリにあることを確認できます。 たとえば、ドメインのドメイン管理者としてログオンしているユーザーの場合、ログファイルは次の場所にあります。 C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. [**Active Directory の準備**] リンクをクリックします。
    
4. **手順 1: スキーマの準備**
    
    a. 手順 1 の前提条件を確認します。"手順 1" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。
    
    b. 手順 1 の [**実行**] をクリックして、スキーマの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. スキーマが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    •. [**完了**] をクリックしてスキーマの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
5. **手順 2: スキーマ パーティションのレプリケーションの確認**
    
    a. ドメインのドメイン コントローラーにログオンします。
    
    b. [**サーバー マネージャー**] の [**ツール**] ドロップダウン メニューから [**ADSI エディター**] を開きます。
    
    c. [**アクション**] メニューで、[**接続**] をクリックします。
    
    d. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
    •. スキーマ コンテナーで、**CN=ms-RTC-SIP-SchemaVersion** を検索します。 このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。 このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。
    
6. **手順 3: 現在のフォレストの準備**
    
    a. 手順 3 の前提条件を確認します。"手順 3" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。
    
    b. 手順 3 の [**実行**] をクリックして、現在のフォレストの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ユニバーサル グループを作成するドメインを指定します。 サーバーがドメインの一部である場合は、[**ローカル ドメイン**] を選択して、[**次へ**] をクリックします。
    
    •. フォレストが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    f. [**完了**] をクリックして現在のフォレストの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
    agdlp. [**アプリ**] ページで [ **Skype For Business Server 管理シェル**] をクリックして PowerShell を起動します。
    
    ア. コマンドの Get-CsAdForest を入力して、 **enter**キーを押します。
    
    私。 結果が**LC_FORESTSETTINGS_STATE_READY**場合は、図に示すように、フォレストが正常に準備されています。
    
     ![フォレスト レプリケーションの確認](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **手順 4: グローバル カタログのレプリケーションの確認**
    
    a. フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。
    
    b. [**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。
    
    c. 左側のウィンドウの [**ユーザー**] コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を見つけます。 (先頭に Cs が付いた他の新しいユニバーサル グループと共に) CsAdministrator が表示されている場合、Active Directory のレプリケーションは成功しています。
    
    d. グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。 グループが表示されている場合、レプリケーションは完了しています。
    
8. **手順 5: 現在のドメインの準備**
    
    a. 手順 5 の前提条件の情報を確認します。
    
    b. 手順 5 の [**実行**] をクリックして、現在のドメインの準備ウィザードを起動します。
    
    c. 手順は、展開のドメインごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ドメインが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    •. [**完了**] をクリックして現在のドメインの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
    これらの手順は、Skype for Business Server オブジェクトが検出されたすべてのドメインで完了する必要があります。そうでないと、サービスが開始されないことがあります。 オブジェクトには、ユーザー、連絡先オブジェクト、管理グループなどのすべての種類の Active Directory オブジェクトや、他のすべての種類のオブジェクトが含まれます。 Set-CsUserReplicatorConfiguration-ADDomainNamingContextList を使って、必要に応じて、Skype for Business Server オブジェクトでドメインのみを追加することができます。
    
9. **手順 6: ドメイン内のレプリケーションの確認**
    
    a. [**アプリ**] ページから**Skype For Business Server 管理シェル**をクリックして PowerShell を起動します。
    
    b. コマンドの Get-CsAdDomain を使用して、ドメイン内の複製を確認します。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 
  
    contoso.local ドメインのコマンドの実行例:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する AD DS フォレストのルートに 1 つのドメイン コントローラーを定義します。グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。 
  
    c. 結果が**LC_DOMAINSETTINGS_STATE_READY**場合は、ドメインが正常に複製されています。
    
10. **手順 7: Skype for Business Server コントロール パネルへの管理アクセスを提供するためのユーザーの追加**
    
    a. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    b. [**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーをクリックし、CSAdministrator を右クリックして、[**プロパティ**] を選択します。
    
    c. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
    d. [**メンバー**] タブで [**追加**] をクリックします。 [**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。 CSAdministrators グループに追加するユーザー名またはグループ名を入力します。 **[OK]** をクリックします。
    
    •. [**メンバー**] タブで、選択したユーザーまたはグループが表示されていることを確認します。 [**OK**] をクリックします。
    
    > [!CAUTION]
    > Skype for Business Server コントロールパネルは、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップにより、Skype for Business Server コントロールパネルを使用しているユーザーは、使用可能なすべての構成機能に対してフルコントロールを利用できます。 特定の機能向けに設計されたその他の役割も使用できます。 利用可能な役割の詳細については、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」および「 [Skype for business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。 管理グループのメンバーになるためには、ユーザーが Skype for Business Server を有効にする必要はありません。 
  
    > [!CAUTION]
    > セキュリティとロールベースのアクセス制御の整合性を維持するために、ユーザーが Skype for Business Server 展開の管理で実行する役割を定義するグループにユーザーを追加します。 
  
11. [ログオフ] をクリックして、新しい Skype for Business Server セキュリティグループでセキュリティトークンが更新されるように、Windows に再度ログオンします。次に、展開ウィザードをもう一度開きます。
    
12. 図に示すように、[ **Active Directory の準備**] の横に緑色のチェックマークが表示されていることを確認します。
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>関連項目
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
