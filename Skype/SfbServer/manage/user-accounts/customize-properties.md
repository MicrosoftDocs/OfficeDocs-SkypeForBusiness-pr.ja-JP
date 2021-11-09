---
title: ユーザー アカウントのプロパティをカスタマイズSkype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: このセクションの手順を使用して、個々のユーザー アカウントのプロパティを変更できます。
ms.openlocfilehash: c2a2f63e31d17e90cea528c3fc8ef88dd1952902
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856654"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a>ユーザー アカウントのプロパティをカスタマイズSkype for Business Server
 
このセクションの手順を使用して、個々のユーザー アカウントのプロパティを変更できます。
  
個々のユーザー レベルで実行できる 2 つの基本的な操作があります。
  
- [特定のユーザー アカウントのテレフォニー オプションを構成する](customize-properties.md#Tel_Op)
    
- [ユーザーを別のプールに移動する](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a>特定のユーザー アカウントのテレフォニー オプションを構成する
<a name="Tel_Op"> </a>

特定のユーザーのテレフォニー設定をカスタマイズできます (個々のユーザーがユーザーに対して有効にされ、Skype for Business Serverがテレフォニーをサポートしている限り)。
  
Skype for Business Serverテレフォニー オプションには、次のものが含まれます。
  
- **オーディオ/ビデオが無効** ユーザーは、オーディオとビデオを使用して通話を行う必要があります。
    
- **PC 間のみ** ユーザーは PC 間の音声通話またはビデオ通話のみを行います。
    
- **エンタープライズ VoIP** ユーザーは、すべての着信および発信Skype for Business Serverインフラストラクチャを使用してルーティングできます。 また、PC 間の通話も可能です。
    
- **リモート通話制御** ユーザーは、Skype for Business Serverを使用してデスクトップ電話を制御し、PC 間通話を行う場合にも使用できます。
    
組織のテレフォニーの構成の詳細については、「展開」のドキュメントの[「Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)の エンタープライズ VoIP のユーザー[](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md)を有効にする」および「エンタープライズ VoIP Skype for Business Server を展開する」を参照してください。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. **[ユーザーの検索]** ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、**[検索]** をクリックします。
    
5. 表中の変更するユーザー アカウントをクリックします。
    
6. [**編集**] メニューの [**変更**] をクリックします。
    
7. [**テレフォニー**] で次の操作を行います。
    
   - ユーザーの音声通話およびビデオ通話を無効にするには、**[音声ビデオを無効にする]** をクリックします。
    
   - ユーザーの PC 間の音声通信を有効にするが、リモート通話コントロールやエンタープライズ VoIP は有効にしない場合は、[**PC 間のみ**] をクリックします。 ユーザーが PC 間の音声通信に使用する電話の [**回線 URI**] の値を指定します。
    
   - PC 間オーディオ通信を含むサービス ポリシーのクラスに従って Skype for Business インフラストラクチャを使用してユーザーの電話をルーティングするには、[エンタープライズ VoIP]**をクリックします**。 [**回線 URI**] でエンタープライズ VoIP の電話番号を指定します。 [**ダイヤル プラン ポリシー**] と [**音声ポリシー**] で、ユーザーの適切なポリシーを指定します。 ユーザーのダイヤルした電話番号を E.164 形式に変換するための正規化ルールを指定するには、[**場所のポリシー**] で適切な場所のプロファイルを選択します。
    
   - ユーザーが Skype for Business Server からデスクトップ電話回線を制御して PC 間通話と PC 間通話を行うリモート通話制御を有効にするには、[リモート通話制御] をクリック **します**。 [**回線 URI**] でリモート通話コントロールの電話番号を指定します。 通話ルーティングを行うには、ユーザーがデスクトップ電話と構内交換機 (PBX) を持っている必要があります。
    
## <a name="move-users-to-another-pool"></a>ユーザーを別のプールに移動する
<a name="Move_Users"> </a>

[コントロール パネル] Skype for Business Serverを使用して、ユーザーを特定のサーバーまたはプールに割り当てできます。
  
> [!TIP]
> Lync Server 2010 以前を実行しているソース プールから、複雑な Active Directory 環境の Skype for Business Server 宛先プールに既存のすべてのユーザーを移動すると、Active Directory のレプリケーションが遅くなる可能性があります。 これを回避するには、検索フィルターを使用して、Lync Server 2010 以前を実行しているプールからユーザーを個別に移動するか、Skype for Business Server 管理シェルを使用してコマンドレットを使用してユーザーを移動できます。 また、フィルター機能は、ユーザーのSkype for Business Serverします。 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a>選択したユーザーを別のサーバーまたはプールに移動するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
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
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。
    
5. [**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。
    
6. [**移動先レジストラ プール**] で、ユーザーの移動先のプールを選択します。
    
7. (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。
    
    > [!CAUTION]
    > [**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>フィルターを使用してユーザーをプール間で移動するには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。 
    
3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。
    
4. [ **ユーザー検索] で**、[検索] **をクリック** し、[フィルターの追加] **をクリックします**。
    
5. 検索条件で [**レジストラー プール**] を選択し、[**が次の値に等しい**] を選択して、[**現在のプールの FQDN**] を選択し、[**検索**] をクリックします。
    
6. [**アクション**] メニューの [**すべてのユーザーをプールに移動**] をクリックします。
    
    > [!NOTE]
    > 既存のユーザー セットに対してフィルターを適用すると、オプション [**すべてのユーザーをプールに移動**] は、可能性のあるユーザーすべてではなく、フィルターされたユーザーのサブセットのコンテキストとなります ****。
  
7. [**ユーザーの移動**] の [**移動元レジストラー プール**] で、移動するユーザー アカウントが入っているプールを選択します。
    
8. [**移動先レジストラー プール**] で、ユーザーの移動先のプールを選択します。
    
9. (オプション) 移動先のサーバーまたはプールを使用できない場合は、[**強制**] チェック ボックスをオンにします。
    
    > [!CAUTION]
    > [**強制**] を選択すると、ユーザー アカウントは移動しますが、関連付けられているユーザー データ (ユーザーが予約した会議、連絡先など) がすべて削除されます。選択しない場合は、アカウントも関連付けられているデータも移動します。 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Powershell コマンドレットを使用して、あるプールから別のプールWindows移動するには

1. Windows PowerShell コマンドの実行方法 (ローカルまたはリモート) に応じて、次のように正しい Skype for Business Server 管理役割のメンバーとしてログオンする必要があります。
    
   a. ローカル コンピューターでコマンドを実行している場合 (たとえば、フロント エンド サーバーに直接ログオンします):Skype for Business Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとしてインストールされているコンピューターにログオンするか、「Delegate **Setup Permissions」** の説明に従って必要なユーザー権限を持つコンピューターにログオンします。
    
   b. 別のコンピューターでリモートでコマンドを実行している場合 (たとえば、コンピューターにログオンし、Standard Edition フロント エンド サーバーでリモートでコマンドを実行する): CsUserAdministrator 役割または CsAdministrator 役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする: [**スタート**] をクリックし、[すべてのプログラム] をクリックし、[Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
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


