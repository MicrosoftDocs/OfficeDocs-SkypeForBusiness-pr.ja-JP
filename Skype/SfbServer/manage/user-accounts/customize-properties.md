---
title: Skype for Business Server のユーザー アカウント プロパティをカスタマイズする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: このセクションの手順を使用して、個々のユーザー アカウントのプロパティを変更できます。
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826267"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>Skype for Business Server のユーザー アカウント プロパティをカスタマイズする
 
このセクションの手順を使用して、個々のユーザー アカウントのプロパティを変更できます。
  
個々のユーザー レベルで実行できる基本的な操作は 2 種類です。
  
- [特定のユーザー アカウントのテレフォニー オプションを構成する](customize-properties.md#Tel_Op)
    
- [ユーザーを別のプールに移動する](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>特定のユーザー アカウントのテレフォニー オプションを構成する
<a name="Tel_Op"> </a>

特定のユーザーのテレフォニー設定をカスタマイズできます (個々のユーザーが Skype for Business Server に対して有効で、組織がテレフォニーをサポートしている場合)。
  
Skype for Business Server のユーザー テレフォニー オプションには、次のものがあります。
  
- **オーディオ/ビデオが無効** ユーザーは、音声とビデオを使用して通話を行う必要があります。
    
- **PC 間のみ** ユーザーは PC 間の音声通話またはビデオ通話のみを行います。
    
- **エンタープライズ VoIP** ユーザーは、Skype for Business Server インフラストラクチャを使用して、すべての着信および発信通話をルーティングできます。 また、PC 間の通話も可能です。
    
- **リモート通話コントロール** ユーザーは Skype for Business Server を使用してデスクトップ電話を制御し、PC 間呼び出しを行います。
    
組織のテレフォニーの構成の詳細については、「展開」のドキュメントの [「Enable users for エンタープライズ VoIP in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and Deploy エンタープライズ VoIP in Skype for Business [Server」](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) を参照してください。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、**[検索]** をクリックします。
    
5. 表中の変更するユーザー アカウントをクリックします。
    
6. [**編集**] メニューの [**変更**] をクリックします。
    
7. [**テレフォニー**] で次の操作を行います。
    
   - ユーザーの音声通話およびビデオ通話を無効にするには、**[音声ビデオを無効にする]** をクリックします。
    
   - ユーザーの PC 間の音声通信を有効にするが、リモート通話コントロールやエンタープライズ VoIP は有効にしない場合は、[**PC 間のみ**] をクリックします。 ユーザーが PC 間の音声通信に使用する電話の [**回線 URI**] の値を指定します。
    
   - PC 間の音声通信を含むサービス ポリシーのクラスに従って、Skype for Business インフラストラクチャを使用してユーザーの電話をルーティングするには、[エンタープライズ VoIP ] をクリック **します。** [**回線 URI**] でエンタープライズ VoIP の電話番号を指定します。 [**ダイヤル プラン ポリシー**] と [**音声ポリシー**] で、ユーザーの適切なポリシーを指定します。 ユーザーのダイヤルした電話番号を E.164 形式に変換するための正規化ルールを指定するには、[**場所のポリシー**] で適切な場所のプロファイルを選択します。
    
   - ユーザーが Skype for Business Server からデスクトップ電話回線を制御して PC 間通話と PC 間通話を行うリモート通話コントロールを有効にするには、[リモート通話コントロール] をクリック **します**。 [**回線 URI**] でリモート通話コントロールの電話番号を指定します。 通話ルーティングを行うには、ユーザーがデスクトップ電話と構内交換機 (PBX) を持っている必要があります。
    
## <a name="move-users-to-another-pool"></a>ユーザーを別のプールに移動する
<a name="Move_Users"> </a>

Skype for Business Server コントロール パネルを使用して、ユーザーを特定のサーバーまたはプールに割り当てできます。
  
> [!TIP]
> Lync Server 2010 以前を実行している送信元プールから複雑な Active Directory 環境内の Skype for Business Server のレプリケーション先プールに既存のすべてのユーザーを移動すると、Active Directory レプリケーションの速度が低下する可能性があります。 これを回避するには、検索フィルターを使用して、Lync Server 2010 以前を実行しているプールからユーザーを個別に移動するか、Skype for Business Server 管理シェルを使用してコマンドレットを使用してユーザーを移動できます。 また、フィルター機能は Skype for Business Server ユーザーと一緒に動作します。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>選択したユーザーを別のサーバーまたはプールに移動するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. [**ユーザーの検索**] ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、[**検索**] をクリックします。 
    
5. 表の一覧で、特定のユーザーまたは複数のユーザーを選択します。 
    
6. [**アクション**] メニューの [**選択したユーザーをプールに移動する**] をクリックします。
    
7. [**ユーザーの移動**] の [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。
    
8. (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制移動**] チェック ボックスをオンにします。
    
    > [!CAUTION]
    > [**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>サーバー間またはプール間ですべてのユーザーを移動するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。
    
5. [**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。
    
6. [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。
    
7. (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。
    
    > [!CAUTION]
    > [**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>フィルターを使用してユーザーをプール間で移動するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。 
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. ユーザー **検索で、[** 検索] を **クリックし**、[フィルターの追加] **をクリックします**。
    
5. 検索条件で [**レジストラー プール**] を選択し、[**が次の値に等しい**] を選択して、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。
    
6. [**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。
    
    > [!NOTE]
    > 既存のユーザー セットに対してフィルターを適用すると、オプション [**すべてのユーザーをプールに移動**] は、可能性のあるユーザーすべてではなく、フィルターされたユーザーのサブセットのコンテキストとなります ****。
  
7. [**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。
    
8. [**移動先レジストラー プール**] で、ユーザーの移動先のプールを選択します。
    
9. (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。
    
    > [!CAUTION]
    > [**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議、連絡先など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用してユーザーをプール間で移動するには

1. Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のように正しい Skype for Business Server 管理者の役割のメンバーとしてログオンする必要があります。
    
   a.  ローカル コンピューターでコマンドを実行している場合 (たとえば、フロントエンド サーバーに直接ログオンする場合): Skype for Business Server 管理シェルがインストールされているコンピューターに RTCUniversalServerAdmins グループのメンバーとして、またはセットアップのアクセス許可の委任の説明に従って必要なユーザー権限を使用してログオンします。
    
   b. 別のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンし、Standard Edition フロントエンド サーバーでリモートでコマンドを実行する場合): CsUserAdministrator の役割または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
3. 単一のユーザーを移動するには、Move-CsUser コマンドレットを次のように使用します。
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    この場合、移動するユーザーは Pilar Ackerman で、現在割り当てられているホーム プールから、プール pool01.contoso.net に移動します。
    
4. 大量のユーザーを移動するには、フィルターと **Get-CsUser** コマンドレットを使用し、ユーザーの結果セットを **Move-CsUser** に渡します。
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    **Get-CsUser** と **Move-CsUser** を組み合わせたコマンドを実行すると、たとえば、次のような結果が得られます。
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


