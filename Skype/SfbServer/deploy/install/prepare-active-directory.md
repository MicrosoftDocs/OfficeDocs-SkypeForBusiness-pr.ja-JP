---
title: Skype for Business Server 2015 用の Active Directory の準備
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: '概要: ビジネス サーバー 2015 の Skype のインストールの場合、Active Directory ドメインを準備する方法を説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 0e031cc16bef00fc7b1ca8c2bd910fd0d36d5dde
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500992"
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 用の Active Directory の準備
 
**の概要:** ビジネス サーバー 2015 の Skype のインストールの場合、Active Directory ドメインを準備する方法について説明します。 [マイクロソフト評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)からサーバー 2015 をビジネス用には、Skype の無料試用版をダウンロードします。
  
Skype ビジネス サーバーは、Active Directory と緊密に動作します。 Skype でビジネスのサーバーを使用する Active Directory ドメインを準備する必要があります。 このプロセスは展開ウィザードで行われ、ドメインに対して 1 回だけ実行されます。 これは、プロセスではグループを作成してドメインを変更しますが、その処理は 1 回だけ必要であるためです。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 Active Directory の準備は、8 つの手順の 4 番目です。 Active Directory の計画の詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory の準備

ビジネス サーバー 2015 の Skype は、Active Directory ドメイン サービス (AD DS) と緊密に統合します。 ビジネス サーバー 2015 の Skype をインストールするには、最初に、Active Directory を準備する必要があります。 展開ウィザードが**Active Directory の準備**をという名前のセクションでは、ビジネスのサーバーの Skype で使用するための Active Directory 環境を準備します。
  
> [!NOTE]
> ビジネス サーバー 2015 の Skype では、追跡し、すべてのトポロジ内のサーバーと通信する (AD DS) を使用します。 Skype ビジネス サーバーが正常に動作できるように、すべてのサーバーをドメインに参加する必要があります。 
  
> [!IMPORTANT]
> "Active Directory の準備" の手順は、展開のドメインごとに 1 回だけ実行する必要があります。 
  
**Active Directory の準備**手順に関するビデオをご覧ください。
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>展開ウィザードからの Active Directory の準備

1. Active Directory ドメインの Schema Admins の資格情報を持つユーザーとしてログオンします。
    
2. Skype をビジネス サーバーの展開ウィザードを開きます。
    
    > [!TIP]
    > ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認するには場合、は、展開ウィザードが実行しているコンピューターの手順を実行する AD DS ユーザーのユーザー ディレクトリ内にそれらを検索できます。 などの場合は、ユーザーとしてログオン ドメイン管理者、ドメイン、contoso.local、ログ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp。 
  
3. [**Active Directory の準備**] リンクをクリックします。
    
4. **ステップ 1: スキーマを準備します。**
    
    a. 手順 1 の前提条件を確認します。"手順 1" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。
    
    b. 手順 1 の [**実行**] をクリックして、スキーマの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. スキーマが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    e。 [**完了**] をクリックしてスキーマの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
5. **手順 2: スキーマ パーティションのレプリケーションを確認します。**
    
    a. ドメインのドメイン コントローラーにログオンします。
    
    b. [**サーバー マネージャー**] の [**ツール**] ドロップダウン メニューから [**ADSI エディター**] を開きます。
    
    c. [**アクション**] メニューで、[**接続**] をクリックします。
    
    d. [**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。
    
    e。 スキーマ コンテナーで、**CN=ms-RTC-SIP-SchemaVersion** を検索します。 このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。 このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。
    
6. **ステップ 3: 現在のフォレストを準備します。**
    
    a. 手順 3 の前提条件を確認します。"手順 3" というタイトルの下にあるドロップダウンをクリックすると、この情報を参照できます。
    
    b. 手順 3 の [**実行**] をクリックして、現在のフォレストの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ユニバーサル グループを作成するドメインを指定します。 サーバーがドメインの一部である場合は、[**ローカル ドメイン**] を選択して、[**次へ**] をクリックします。
    
    e。 フォレストが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    f。 [**完了**] をクリックして現在のフォレストの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
    g です。 PowerShell を起動する**アプリケーション**のページから**Skype ビジネス サーバー管理シェル**をクリックします。
    
    h。 Get-CsAdForest、コマンドを入力し、 **Enter**キーを押します。
    
    私。 結果が**LC_FORESTSETTINGS_STATE_READY**の場合は、フォレストが正常に準備されて、図に示すように。
    
     ![フォレスト レプリケーションの確認](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **手順 4: グローバル カタログのレプリケーションを確認します。**
    
    a. フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。
    
    b. [**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。
    
    c. 左側のウィンドウの [**ユーザー**] コンテナーをクリックし、右側のウィンドウでユニバーサル グループ **CsAdministrator** を見つけます。 (先頭に Cs が付いた他の新しいユニバーサル グループと共に) CsAdministrator が表示されている場合、Active Directory のレプリケーションは成功しています。
    
    d. グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。 グループが表示されている場合、レプリケーションは完了しています。
    
8. **手順 5: 現在のドメインを準備します。**
    
    a. 手順 5 の前提条件の情報を確認します。
    
    b. 手順 5 の [**実行**] をクリックして、現在のドメインの準備ウィザードを起動します。
    
    c. 手順は、展開のドメインごとに 1 回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ドメインが準備されれば、[**ログの表示**] をクリックするとログを表示できます。 
    
    e。 [**完了**] をクリックして現在のドメインの準備ウィザードを閉じ、"Active Directory の準備" の手順に戻ります。
    
    Skype ビジネス サーバー オブジェクトが見つかったら、それ以外の場合サービスがすべてのドメインで、次の手順を完了する必要があるされません。 オブジェクトには、ユーザー、連絡先オブジェクト、管理グループなどのすべての種類の Active Directory オブジェクトや、他のすべての種類のオブジェクトが含まれます。 必要な場合は、ドメインを追加するだけ、Skype で、ビジネスのサーバー オブジェクトのセット CsUserReplicatorConfiguration ADDomainNamingContextList を使用できます。
    
9. **手順 6: ドメイン内のレプリケーションを確認します。**
    
    a. PowerShell を起動する**アプリケーション**のページから**ビジネス サーバー管理シェルの Skype**をクリックします。
    
    b. Get CsAdDomain コマンドを使用すると、ドメイン内のレプリケーションを確認します。
    
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
  
    c. 結果が**LC_DOMAINSETTINGS_STATE_READY**の場合は、ドメインが正常に複製されます。
    
10. **手順 7: ビジネス サーバーのコントロール パネルの管理アクセス権を Skype に提供するためのユーザーを追加します。**
    
    a. Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    b. [**Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して [**ユーザー**] コンテナーをクリックし、CSAdministrator を右クリックして、[**プロパティ**] を選択します。
    
    c. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
    d. [**メンバー**] タブで [**追加**] をクリックします。 [**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。 CSAdministrators グループに追加するユーザー名またはグループ名を入力します。 [**OK**] をクリックします。
    
    e。 [**メンバー**] タブで、選択したユーザーまたはグループが表示されていることを確認します。 [**OK**] をクリックします。
    
    > [!CAUTION]
    > ビジネス サーバーのコントロール パネルの Skype は、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップは、利用可能なすべての構成機能のビジネス サーバーのコントロール パネルの [フル コントロールの Skype を使用しているユーザーを与えます。 特定の機能向けに設計されたその他の役割も使用できます。 使用できるロールの詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。 管理グループのメンバーになるために Skype ビジネス サーバーに対して有効にするユーザーがないことに注意してください。 
  
    > [!CAUTION]
    > セキュリティとロール ベースのアクセス制御の整合性を確保するため、ユーザーがビジネス サーバー配置の Skype の管理を実行するどのような役割を定義するグループにユーザーを追加します。 
  
11. ログオフし、再びログオン Windows ビジネス サーバー セキュリティ グループでは、新しい Skype のユーザーのセキュリティ トークンが更新されるようと、展開ウィザードを再度開きます。
    
12. 図のように、[**Active Directory の準備**] の横に成功を示す緑色のチェックマークが表示されていることを確認します。
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>関連項目
 
[ビジネス サーバー 2015 の Skype の active Directory ドメイン サービス](../../plan-your-deployment/security/active-directory-domain-services.md)