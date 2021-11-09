---
title: ユーザー アカウントを管理Skype for Business Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事のセクションでは、Active Directory ユーザーを有効、一時的に無効、または削除する方法について説明Skype for Business Server。
ms.openlocfilehash: 0bdb2e1d8319a3e4c6379a2563f5d858c3648a77
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856644"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>ユーザー アカウントを管理Skype for Business Server

この記事のセクションでは、Active Directory ユーザーを有効、一時的に無効、または削除する方法について説明Skype for Business Server。

Active Directory ユーザーを有効にする方法については、「Create a New User [Account」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11))。 Active Directory ユーザーを削除する方法については、「ユーザー アカウントの削除 [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。

これらの手順は、メンテナンス 期間中に実行する必要があります。使用Skype for Business最も低い場合。 これが毎日または毎週のスケジュールで行われるかどうかは、組織のニーズによって決まります。

この記事には、次の手順が含まれます。

- [1 つ以上のユーザーを検索するには](user-accounts.md#Search)

- [新しいユーザーを追加して有効Skype for Business Serverする](user-accounts.md#Add)

- [以前に有効にしたユーザー アカウントを無効または再Skype for Business Server](user-accounts.md#Disable)

- [ユーザーがユーザーを無効エンタープライズ VoIP](user-accounts.md#Disable_EV)

- [管理シェルを使用してユーザー Skype for Business Serverを削除する](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>1 つ以上のユーザーを検索するには
<a name="Search"> </a>

検索クエリの結果を使用して、Active Directory ユーザーに対してユーザーを構成Skype for Business Server。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。

[コントロール パネル] または [Active Directory ユーザー Skype for Business Serverコンピューター] スナップインを使用して、ユーザーを検索できます。 次の手順では、コントロール パネルを使用してSkype for Business Serverを検索する方法について説明します。

> [!NOTE]
> 中央フォレスト トポロジがある環境では、ユーザーの電子メール アドレスでユーザーを検索すると、検索結果が正確ではない可能性があります。 代わりに、SIP アドレスプレフィックス (sip:name など) を指定してユーザーを検索したり、検索フィルターを追加したり、部分的な電子メール アドレスを含む SIP アドレスを選択したり **、Get-CSUser** コマンドレットを使用することができます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。

   a. 画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。

   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。

   c. [**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。

   d. テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。

6. [**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>新しいユーザーを追加して有効Skype for Business Serverする
<a name="Add"> </a>

Active Directory ユーザーとコンピューターでユーザー アカウントを有効にした後、Skype for Business Server コントロール パネルを使用して、Active Directory ユーザーを Skype for Business Server に追加して、新しい Skype for Business Server ユーザー アカウントを作成して有効にできます。

コマンドレット (特に [Enable-CsUser) を使用することもできます](/powershell/module/skype/enable-csuser)。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの有効化**] をクリックします。

5. [**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。

6. [**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

7. 表で、ユーザーに追加するアカウントを選択Skype for Business Serverし **、[OK] をクリックします**。

8. ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>以前に有効にしたユーザー アカウントを無効または再Skype for Business Server
<a name="Disable"> </a>

次の手順を使用すると、ユーザー アカウント用に構成した Skype for Business Server 設定を失わずに、Skype for Business Server Skype for Business Server で以前に有効にしたユーザー アカウントを無効にできます。 ユーザー アカウントの設定Skype for Business Server失わないので、ユーザー アカウントを再構成することなく、以前に有効にしたユーザー アカウントを再度有効にできます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. 表で、無効または再度有効にするユーザー アカウントをクリックします。

6. [**アクション**] メニューで、次のいずれかを実行します。

   - ユーザー アカウントを一時的に無効にするには、[Lync Server Skype for Business Server **一時的に無効にする] をクリックします**。

   - ユーザー アカウントを有効にするには、[Lync Server Skype for Business Server再 **有効化] をクリックします**。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Powershell Windowsを使用してユーザー アカウントを無効または再有効化する

ユーザー アカウントは **、Set-CsUser** コマンドレットを使用して、一時的に無効にしてから、後で再び有効にすることができます。 このコマンドレットは、管理者管理シェルSkype for Business Serverリモート セッションから実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。

### <a name="to-disable-a-user-account"></a>ユーザー アカウントを無効にするには

- ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>ユーザー アカウントを再び有効にするには

- 無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

詳細については [、Set-CsUser](/powershell/module/skype/set-csuser) コマンドレットのヘルプ トピックを参照してください。

## <a name="disable-a-user-for-enterprise-voice"></a>ユーザーがユーザーを無効エンタープライズ VoIP
<a name="Disable_EV"> </a>

次の手順を使用して、エンタープライズ VoIPに対して有効になっているユーザー アカウントのユーザー アカウントを無効Skype for Business Server。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>ユーザー アカウントを無効にするには、エンタープライズ VoIP

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。

4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。

5. 表で、ユーザー アカウントで有効にするユーザー アカウントをクリックエンタープライズ VoIP。

6. [**編集**] メニューの [**詳細の表示**] をクリックします。

7. [**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。

    > [!NOTE]
    > Lync を使用してユーザーが音声通話またはビデオ通話を行うのを制限するには、[ **テレ** フォニー] の下の [オーディオ **/ビデオが無効] をクリックします**。

8. [**確定**] をクリックします。

これで、ユーザーは新しい機能をエンタープライズ VoIPしています。 関連情報: <br/>[エンタープライズ VoIPモビリティ](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [ユーザーがユーザーのエンタープライズ VoIPを有効Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 管理シェル](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>管理シェルを使用してユーザー Skype for Business Serverを削除する
<a name="Remove"> </a>

次の手順を使用して、以前に追加したユーザー アカウントを削除Skype for Business Server。

> [!NOTE]
> ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。 代わりにユーザー アカウントを一時的に無効にする場合は、「以前に有効にしたユーザー アカウントを無効または再有効化する」を参照[Skype for Business Server。](user-accounts.md#Disable)

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理者 URL を入力して[コントロール パネル] Skype for Business Server開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. 表で、削除するユーザー アカウントをクリックします。

6. [**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。

7. ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Powershell コマンドレットを使用してユーザー Windowsを削除する

ユーザー アカウントは、このコマンドレットを使用Disable-CsUserできます。 このコマンドレットは、管理シェルからSkype for Business Serverリモート セッション から実行Windows PowerShell。 リモート サーバーを使用してサーバー Windows PowerShellする方法[Skype for Business Server、Microsoft Lync リモート PowerShell 管理を参照してください](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 このプロセスは、同じSkype for Business Server。

### <a name="to-remove-a-user-account"></a>ユーザー アカウントを削除するには
ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。次に例を示します。

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

このコマンドを実行した後、削除したアカウントおよびその以前の設定を再度有効化することはできません。Enable-CsUser コマンドレットを使用して、Ken Myer の新規アカウントを作成する必要があります。

詳細については [、Disable-CsUser コマンドレット](/powershell/module/skype/disable-csuser) のヘルプ トピックを参照してください。

## <a name="see-also"></a>関連項目
<a name="Remove"> </a>

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
