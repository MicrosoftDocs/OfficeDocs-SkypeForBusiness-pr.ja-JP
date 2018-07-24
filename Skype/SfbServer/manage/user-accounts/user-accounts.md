---
title: Skype のビジネス サーバーのユーザー アカウントを管理します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この資料のセクションでは、有効にする、一時的に無効化、または、Skype のビジネス サーバーの Active Directory ユーザーを削除する方法について説明します。
ms.openlocfilehash: ee6a82c5b5def06866379467beddae788d85171b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976738"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Skype のビジネス サーバーのユーザー アカウントを管理します。
 
この資料のセクションでは、有効にする、一時的に無効化、または、Skype のビジネス サーバーの Active Directory ユーザーを削除する方法について説明します。
  
Active Directory のユーザーを有効にする方法については、[新しいユーザー アカウントを作成する](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)を参照してください。 Active Directory ユーザーを削除する方法については、[ユーザー アカウントを削除する](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)を参照してください。
  
ビジネスを使用するための Skype が最も低いときに、メンテナンス時間をこれらの手順を実行する必要があります。 日単位または週単位のスケジュールでこれはあるかどうかは、組織のニーズによって決定されます。 
  
この資料には、次の手順が含まれています。
  
- [1 つまたは複数のユーザーを検索するには](user-accounts.md#Search)
    
- [追加し、ビジネスのサーバーのユーザーの新しい Skype を有効にします。](user-accounts.md#Add)
    
- [無効にするか、既に有効になっている Skype のビジネス サーバーのユーザー アカウントを再度有効にします。](user-accounts.md#Disable)
    
- [エンタープライズ VoIP のユーザーを無効にします。](user-accounts.md#Disable_EV)
    
- [ビジネス サーバー管理シェルには、Skype でのユーザー アカウントを削除します。](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a>1 つまたは複数のユーザーを検索するには
<a name="Search"> </a>

検索クエリの結果を使用すると、Skype のビジネス サーバーの Active Directory ユーザーを構成します。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。
  
ビジネス サーバーのコントロール パネルまたは Active Directory ユーザーを Skype を使用してユーザーを検索でき、スナップインのコンピューターです。 次の手順では、ビジネス サーバーのコントロール パネルの Skype を使用してユーザーを検索する方法について説明します。
  
> [!NOTE]
> 中央フォレスト トポロジの環境で検索結果があります正確なユーザーの電子メール アドレスでユーザーを検索する場合。 代わりに、SIP アドレス プレフィックス sip: 名などを指定することでユーザーを検索し、検索フィルターを追加部分のメール アドレスが含まれている SIP アドレスを選択または**Get CSUser**コマンドレットを使用します。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. **ユーザーが検索**ボックス、すべての種類または表示名、名、姓、名、SAM アカウント名の最初の部分では、SIP アドレス、または行を検索して、[**検索**] をクリックするユーザー アカウントの URI。
    
5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。
    
   a. **検索の結果**、上の画面の右上隅の矢印ボタンをクリックし、[**フィルターの追加**] をクリックします。
    
   b. それを入力するか、ユーザーのプロパティを選択するドロップダウン リストの矢印をクリックすると、ユーザーのプロパティを入力します。
    
   c. **等しい**] ボックスの一覧では、**等しい**か**等しくない**をクリックします。
    
   d. テキスト ボックスで、検索結果にフィルターを使用する検索条件を入力し、**検索**] をクリックします。
    
6. [**検索結果**] で、検索結果が表示されます。 一覧でいずれかまたはすべてのユーザーを選択し、選択したユーザーの構成タスクを実行できます。
    
## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>追加し、ビジネスのサーバーのユーザーの新しい Skype を有効にします。
<a name="Add"> </a>

Active Directory ユーザーとコンピューター内のユーザー アカウントを有効にすると、Skype をビジネスのサーバーの Active Directory ユーザーを追加することによってビジネスのサーバーのユーザー アカウントの新しい Skype を有効にするを作成してビジネス サーバーのコントロール パネルの Skype を使用できます。
  
[Csuser からの有効にする](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)具体的には、コマンドレットを使用することもできます。
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. **ユーザーを有効にする**] をクリックします。
    
5. **新しい Lync Server のユーザー**ダイアログ ボックスで、[**追加**] をクリックします。
    
6. **ユーザーが検索**ボックス、すべての種類または名前の最初の部分では、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) アカウント名、電子メール アドレス、ユーザー プリンシパル名 (UPN)、または使用する Active Directory ユーザー アカウントの電話番号、し、[**検索**] をクリックします。
    
7. テーブルのビジネス サーバーでは、Skype を追加しアカウントを選択し、し、[ **OK**] をクリックします。
    
8. ユーザーをプールに割り当てる、その他の詳細を指定するは、ユーザーにポリシーを割り当てるし、**を有効にする**] をクリックします。
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>無効にするか、既に有効になっている Skype のビジネス サーバーのユーザー アカウントを再度有効にします。
<a name="Disable"> </a>

Business Server のビジネス サーバー構成設定をユーザー アカウント用の Skype を失うことがなく Skype 内の以前の有効なユーザー アカウントを無効にするのには、次の手順を使用できます。 Skype ビジネス サーバーのユーザー アカウントの設定を失わないようにするためことができます再再度有効にする以前に有効なユーザー アカウント、ユーザー アカウントを再構成することがなく。 
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. **ユーザーが検索**ボックス、すべての種類、または表示名、名、姓、セキュリティ アカウント マネージャー (SAM) アカウント名、SIP アドレス、または行を無効にするか、再度有効にするユーザー アカウントの統一リソース識別子 (URI) の最初の部分で[**検索**] をクリックします。
    
5. テーブルでは、ユーザー アカウントを無効または再度有効にするをクリックします。
    
6. [**操作**] メニューには、次のいずれかの操作を行います。
    
   - Skype のビジネス サーバーのユーザー アカウントを一時的に無効には、 **Lync Server を一時的に無効にする**をクリックします。
    
   - ビジネスのサーバーでは、Skype のユーザー アカウントを有効に、 **Lync Server を再度有効にする**をクリックします。
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows Powershell を使用して、無効にするか、ユーザー アカウントを再度有効にするには

ユーザー アカウントを一時的に無効になっているし、し、後で再度有効に、**セット CsUser**コマンドレットを使用することができます。 実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-disable-a-user-account"></a>ユーザー アカウントを無効にするには

- ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。 例:
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>ユーザー アカウントを再度有効にするのには

- 無効なユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。 例:
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

詳細については、[セット CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="disable-a-user-for-enterprise-voice"></a>エンタープライズ VoIP のユーザーを無効にします。
<a name="Disable_EV"> </a>

有効になっている Skype ビジネス サーバーのユーザー アカウントでエンタープライズ VoIP を無効にするのにには、次の手順を使用します。
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a>エンタープライズ VoIP のユーザー アカウントを無効にするには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。
    
5. テーブルでは、エンタープライズ VoIP を有効にするユーザー アカウントをクリックします。
    
6. [**編集**] メニューの [**詳細の表示**] をクリックします。
    
7. **Lync Server ユーザーの編集**] ページで、[**テレフォニー**]、[**エンタープライズ VoIP**] 以外のオプションをクリックします。
    
    > [!NOTE]
    > **テレフォニー**では、下の Lync を使用して、音声通話またはビデオ通話をすることからユーザーを制限するには、**オーディオとビデオを無効**をクリックします。 
  
8. [**確定**] をクリックします。
    
ユーザーは、ここでエンタープライズ VoIP 機能を使用することはありません。 関連情報: <br/>[エンタープライズ VoIP およびモバイル](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 管理シェル](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>ビジネス サーバー管理シェルには、Skype でのユーザー アカウントを削除します。
<a name="Remove"> </a>

Skype でビジネスのサーバーに以前に追加したユーザー アカウントを削除するのには、次の手順を使用できます。 
  
> [!NOTE]
> ユーザーを削除する、ユーザー アカウントの設定が失われます。 一時的に代わりに、ユーザー アカウントを無効にしたい場合[を無効または有効にしていた Skype ビジネス サーバー用のユーザー アカウントを再度有効にする](user-accounts.md#Disable)を参照してください。 
  
1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。
    
2. 、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。  
    
3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。
    
4. **ユーザーが検索**ボックス、すべての種類、または表示名、名、姓、セキュリティ アカウント マネージャー (SAM) アカウント名、SIP アドレス、または行を無効にするか、再度有効にするユーザー アカウントの統一リソース識別子 (URI) の最初の部分で[**検索**] をクリックします。
    
5. テーブルで、削除するユーザー アカウントをクリックします。
    
6. [**アクション**] メニューの [選択して、 **Lync Server から削除する**、ダイアログ ボックスが表示されます。
    
7. ダイアログ ボックスからユーザーを削除するのには **[ok]** を選択します。
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用するユーザー アカウントを削除します。

Csuser からの無効化のコマンドレットを使用してユーザー アカウントを削除できます。 ビジネス サーバー管理シェルの Skype から、または Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 プロセスは、Skype のビジネス サーバーで同じです。
  
### <a name="to-remove-a-user-account"></a>ユーザー アカウントを削除するのには
ユーザー アカウントを削除するには、無効にする CsUser コマンドレットを使用します。 例:
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
詳細については、[無効にする CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。
  
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="Remove"> </a>

[Csuser からの有効化](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[Csuser からの無効化](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)