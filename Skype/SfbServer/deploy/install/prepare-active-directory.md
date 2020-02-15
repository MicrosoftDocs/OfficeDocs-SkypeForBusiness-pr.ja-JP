---
title: Skype for Business Server 用の Active Directory の準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について説明します。 次https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverの Microsoft 評価センターから、無料の Skype For business Server の試用版をダウンロードしてください。'
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018178"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Skype for Business Server 用の Active Directory の準備
 
**概要:** Skype for Business Server のインストール用に Active Directory ドメインを準備する方法について説明します。 [Microsoft 評価センター](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)から、無料の Skype For business Server の試用版をダウンロードします。
  
Skype for Business Server は、Active Directory と緊密に連携します。 Skype for Business Server と連携するには、Active Directory ドメインを準備する必要があります。 このプロセスは展開ウィザードで行われ、ドメインに対して1回だけ実行されます。 これは、プロセスによってグループが作成され、ドメインが変更されるため、1回だけ実行する必要があるためです。 手順1から5までを任意の順序で実行できます。 ただし、手順6、7、および8は、図に示されているように、手順 1 ~ 5 の後で実行する必要があります。 Active Directory の準備手順 4/8。 Active Directory の計画の詳細については、「skype for business [server の環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」または「skype For business [server のサーバー要件 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
![概要図](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Active Directory の準備

Skype for Business Server は、Active Directory ドメインサービス (AD DS) と密接に統合されています。 Skype for Business Server を初めてインストールするには、Active Directory を準備する必要があります。 「Active directory を**準備**する」というタイトルの展開ウィザードのセクションでは、active directory 環境で Skype For business Server を使用するように準備します。
  
> [!NOTE]
> Skype for Business Server は (AD DS) を使用して、トポロジ内のすべてのサーバーを追跡して通信します。 これらのサーバーの大部分はドメインに参加して、Skype for Business Server が正常に動作するようにする必要があります。 エッジやリバースプロキシなどのサーバーは、ドメインに参加してはならないことに注意してください。
  
> [!IMPORTANT]
> Active Directory の準備手順は、展開内の各ドメインに対して1回だけ実行する必要があります。 
  
**Active Directory を準備**するためのビデオの手順をご覧ください。
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>展開ウィザードから Active Directory を準備する

1. Active Directory ドメインのスキーマ管理者の資格情報を持つユーザーとしてログオンします。
    
2. Skype for Business Server 展開ウィザードを開きます。
    
    > [!TIP]
    > Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した AD DS ユーザーのユーザーディレクトリに移動します。 たとえば、ユーザーがドメインのドメイン管理者としてログオンしている場合は、ログファイルは次の場所にあります。 C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. [ **Active Directory の準備**] リンクをクリックします。
    
4. **手順 1: スキーマの準備**
    
    a.  手順1の前提条件の情報を確認します。これには、手順1のタイトルの下にあるドロップダウンをクリックしてアクセスできます。
    
    b.  手順1で [**実行**] をクリックして、スキーマの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに1回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. スキーマの準備が整ったら、[**ログの表示**] をクリックしてログを表示することができます。 
    
    e.  [**完了**] をクリックして、スキーマの準備ウィザードを閉じ、[Active Directory の準備] の手順に戻ります。
    
5. **手順 2: スキーマパーティションのレプリケーションを確認する**
    
    a.  ドメインのドメインコントローラーにログオンします。
    
    b.  **サーバーマネージャー**の [**ツール**] ドロップダウンメニューから [ **ADSI エディター** ] を開きます。
    
    c. **[アクション]** メニューで、**[接続]** をクリックします。
    
    d. **[接続の設定]** ダイアログ ボックスの **[既知の名前付けコンテキストを選択する]** で、**[スキーマ]** を選択して **[OK]** をクリックします。
    
    e.  スキーマコンテナーの下で、 **CN = ms-sip-pstn**を検索します。 このオブジェクトが存在し、 **Rangeupper**属性の値が1150で、 **rangeupper**属性の値が3の場合は、スキーマが正常に更新され、レプリケートされています。 このオブジェクトが存在しない場合、または**Rangeupper**属性と**rangeupper**属性の値が指定されていない場合は、スキーマが変更されていないか、レプリケートされていません。
    
6. **手順 3: 現在のフォレストを準備する**
    
    a.  手順3の前提条件の情報を確認します。そのためには、手順3のタイトルの下にあるドロップダウンをクリックしてアクセスできます。
    
    b.  手順3で [**実行**] をクリックして、現在のフォレストの準備ウィザードを起動します。
    
    c. 手順は、展開ごとに1回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ユニバーサルグループを作成するドメインを指定します。 サーバーがドメインの一部である場合は、[**ローカルドメイン**] を選択して、[**次へ**] をクリックします。
    
    e.  フォレストが準備されたら、[**ログの表示**] をクリックしてログを表示することができます。 
    
    f. [**完了**] をクリックして現在のフォレストの準備ウィザードを閉じ、「Active Directory の準備」の手順に戻ります。
    
    g.  [**アプリ**] ページの [ **Skype For Business Server 管理シェル**] をクリックして、PowerShell を起動します。
    
    h. コマンド「Get-help Adforest」と入力し、 **enter**キーを押します。
    
    私。 結果が**LC_FORESTSETTINGS_STATE_READY**場合は、図に示すように、フォレストが正常に準備されています。
    
     ![フォレストレプリケーションを確認します。](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **手順 4: グローバルカタログのレプリケーションを確認する**
    
    a.  フォレストの準備が実行されたフォレスト内のドメインコントローラー (他のドメインコントローラーからリモートサイトにあることが望ましい) で、[ **Active Directory ユーザーとコンピューター**] を開きます。
    
    b.  **[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。
    
    c. 左側のウィンドウで [**ユーザー** ] コンテナーをクリックし、右側のウィンドウでユニバーサルグループ**csadministrator**を探します。 CsAdministrator (Cs で始まる他の新しいユニバーサルグループの中) が存在する場合は、Active Directory のレプリケーションが成功しています。
    
    d. グループがまだ存在しない場合は、レプリケーションを強制するか、15分待ってから右側のウィンドウを更新します。 グループが表示されている場合、レプリケーションは完了しています。
    
8. **手順 5: 現在のドメインを準備する**
    
    a.  手順5の前提条件に関する情報を確認します。
    
    b.  手順5で [**実行**] をクリックして、現在のドメインの準備ウィザードを起動します。
    
    c. 手順は展開内の各ドメインに対して1回だけ実行する必要があることに注意して、[**次へ**] をクリックします。
    
    d. ドメインの準備が整ったら、[**ログの表示**] をクリックしてログを表示することができます。 
    
    e.  [**完了**] をクリックして、現在のドメインの準備ウィザードを閉じ、「Active Directory の準備」の手順に戻ります。
    
    これらの手順は、Skype for Business Server オブジェクトが見つかったすべてのドメインで完了する必要があります。そうでない場合は、サービスが開始されないことがあります。 これには、ユーザー、連絡先オブジェクト、管理グループ、その他の種類のオブジェクトなど、すべての種類の Active Directory オブジェクトが含まれます。 必要に応じて、Set-CsUserReplicatorConfiguration-ADDomainNamingContextList を使用して、Skype for Business Server オブジェクトのあるドメインのみを追加できます。
    
9. **手順 6: ドメインでレプリケーションを確認する**
    
    a.  [**アプリ**] ページの [ **Skype For Business Server 管理シェル**] をクリックして、PowerShell を起動します。
    
    b.  コマンド Get-CsAdDomain を使用して、ドメイン内のレプリケーションを確認します。
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 
  
    Contoso. ローカルドメインのコマンドを実行する例を次に示します。
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を格納する場所を指定できます。 設定がシステムコンテナーに格納されている場合 (これは、構成コンテナーにグローバル設定が移行されていないアップグレード展開で一般的に使用されます)、AD DS フォレストのルートにドメインコントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは、設定が構成コンテナーに格納されていると見なし、Active Directory の任意のドメインコントローラーを参照します。 
  
    c. 結果が**LC_DOMAINSETTINGS_STATE_READY**の場合、ドメインは正常にレプリケートされています。
    
10. **手順 7: Skype for Business Server コントロールパネルへの管理アクセス権を付与するユーザーを追加する**
    
    a.  Domain Admins グループまたは RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
    b.  [ **Active Directory ユーザーとコンピューター**] を開き、ドメインを展開して、[**ユーザー** ] コンテナーをクリックし、[csadministrator] を右クリックして、[**プロパティ**] を選択します。
    
    c. [**CSAdministrator のプロパティ**] で、[**メンバー**] タブをクリックします。
    
    d. [ **メンバー**] タブで [ **追加**] をクリックします。 [**ユーザー、連絡先、コンピューター、サービス アカウント、またはグループの選択**] で、[**選択するオブジェクト名を入力してください**] を見つけます。 CSAdministrators グループに追加するユーザー名またはグループ名を入力します。 **[OK]** をクリックします。
    
    e.  [**メンバー** ] タブで、選択したユーザーまたはグループが存在することを確認します。 **[OK]** をクリックします。
    
    > [!CAUTION]
    > Skype for Business Server コントロールパネルは、役割ベースのアクセス制御ツールです。 CsAdministrator グループのメンバーシップにより、使用可能なすべての構成機能について、Skype for Business Server コントロールパネルを使用しているユーザーがフルコントロールを使用できるようになります。 特定の機能向けに設計されたその他の役割も使用できます。 使用可能なロールの詳細については、「skype for business Server またはサーバー要件」の「 [2019 skype](../../../SfBServer2019/plan/system-requirements.md)for business Server の[環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)」を参照してください。 管理グループのメンバーにするために、ユーザーが Skype for Business Server を有効にする必要はありません。 
  
    > [!CAUTION]
    > セキュリティと役割ベースのアクセス制御の整合性を維持するために、Skype for Business Server 展開の管理においてユーザーが果たす役割を定義するグループにユーザーを追加します。 
  
11. ログオフした後、Windows に再びログオンして、セキュリティトークンが新しい Skype for Business Server セキュリティグループで更新されるようにしてから、展開ウィザードを再び開きます。
    
12. 図に示すように、[ **Active Directory の準備**] が正常に表示されていることを確認します。
    
     ![Active Directory の準備が完了しました。](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>関連項目
 
[Skype for business Server 2015 の Active Directory ドメインサービス](../../plan-your-deployment/security/active-directory-domain-services.md)
