---
title: Skype for Business Server のユーザー アカウントを管理する
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事の各セクションでは、Skype for Business Server から Active Directory ユーザーを有効、一時的に無効、または削除する方法について説明します。
ms.openlocfilehash: aa1b1b21ba089815af20b61da3360179fb10935e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832777"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Skype for Business Server のユーザー アカウントを管理する

この記事の各セクションでは、Skype for Business Server から Active Directory ユーザーを有効、一時的に無効、または削除する方法について説明します。

Active Directory ユーザーを有効にする方法については、「新しいユーザー アカウントを作成 [する」を参照してください](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)。 Active Directory ユーザーを削除する方法については、「ユーザー アカウントを削除 [する」を参照してください](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)。

これらの手順は、Skype for Business の使用が最も少ないメンテナンス期間中に実行する必要があります。 これが毎日または毎週のスケジュールで行われるかどうかは、組織のニーズによって決まります。

この記事には、以下の手順が含まれます。

- [1 つ以上のユーザーを検索するには](user-accounts.md#Search)

- [新しい Skype for Business Server ユーザーを追加して有効にする](user-accounts.md#Add)

- [以前に Skype for Business Server に対して有効にしたユーザー アカウントを無効または再有効化する](user-accounts.md#Disable)

- [ユーザーのアクセスを無効エンタープライズ VoIP](user-accounts.md#Disable_EV)

- [Skype for Business Server 管理シェルを使用してユーザー アカウントを削除する](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>1 つ以上のユーザーを検索するには
<a name="Search"> </a>

検索クエリの結果を使用して、Active Directory ユーザーを Skype for Business Server 用に構成できます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。

Skype for Business Server コントロール パネルまたは Active Directory ユーザーとコンピューター スナップインを使用して、ユーザーを検索できます。 次の手順では、Skype for Business Server コントロール パネルを使用してユーザーを検索する方法について説明します。

> [!NOTE]
> 中央フォレスト トポロジがある環境では、ユーザーの電子メール アドレスでユーザーを検索するときに、検索結果が正確ではない可能性があります。 代わりに、sip:name など、SIP アドレス プレフィックスを指定してユーザーを検索したり、検索フィルターを追加して、部分的な電子メール アドレスを含む SIP アドレスを選択したり **、Get-CSUser** コマンドレットを使用することができます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。

   a.  画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。

   b. ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。

   c. [**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。

   d.  テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。

6. [**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>新しい Skype for Business Server ユーザーを追加して有効にする
<a name="Add"> </a>

Active Directory ユーザーとコンピューターでユーザー アカウントを有効にした後、Skype for Business Server コントロール パネルを使用して、Active Directory ユーザーを Skype for Business Server に追加することで、新しい Skype for Business Server ユーザー アカウントを作成して有効にできます。

コマンドレット、特に [Enable-CsUser を使用することもできます](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの有効化**] をクリックします。

5. [**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。

6. [**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

7. 表で、Skype for Business Server に追加するアカウントを選択し **、[OK]** をクリックします。

8. ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>以前に Skype for Business Server に対して有効にしたユーザー アカウントを無効または再有効化する
<a name="Disable"> </a>

次の手順を使用すると、ユーザー アカウントに対して構成した Skype for Business Server の設定を失わずに、Skype for Business Server で以前に有効にしたユーザー アカウントを無効にできます。 Skype for Business Server のユーザー アカウント設定が失われることはありませんので、ユーザー アカウントを再構成することなく、以前に有効にしたユーザー アカウントを再度有効にできます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. 表で、無効または再度有効にするユーザー アカウントをクリックします。

6. [**アクション**] メニューで、次のいずれかを実行します。

   - Skype for Business Server のユーザー アカウントを一時的に無効にするには、[Lync Server で一時的に無効にする **] をクリックします**。

   - Skype for Business Server のユーザー アカウントを有効にするには、Lync Server の **[再有効化] をクリックします**。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows Powershell を使用してユーザー アカウントを無効または再有効化する

**Set-CsUser** コマンドレットを使用して、ユーザー アカウントを一時的に無効にしてから、後で再び有効にできます。 このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 プロセスは Skype for Business Server でも同じです。

### <a name="to-disable-a-user-account"></a>ユーザー アカウントを無効にするには

- ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。 次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>ユーザー アカウントを再び有効にするには

- 無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。 次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

詳細については [、Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。

## <a name="disable-a-user-for-enterprise-voice"></a>ユーザーのアクセスを無効エンタープライズ VoIP
<a name="Disable_EV"> </a>

Skype for Business Server に対して有効エンタープライズ VoIPアカウントに対して、この設定を無効にするには、次の手順を使用します。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>ユーザー アカウントを無効にするにはエンタープライズ VoIP

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。

4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。

5. 表で、ユーザー アカウントを有効にするユーザー アカウントをエンタープライズ VoIP。

6. [**編集**] メニューの [**詳細の表示**] をクリックします。

7. [**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。

    > [!NOTE]
    > Lync を使用して音声通話やビデオ通話を行うのを制限するには、[ **テレ** フォニー] の [音声/ビデオを無効にする **] をクリックします**。

8. [**確定**] をクリックします。

これで、ユーザーは新しい機能エンタープライズ VoIPできません。 関連情報: <br/>[エンタープライズ VoIPとモビリティ](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Skype for Business Server でエンタープライズ VoIPを有効にする](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 管理シェル](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してユーザー アカウントを削除する
<a name="Remove"> </a>

次の手順を使用して、Skype for Business Server で以前に追加したユーザー アカウントを削除できます。

> [!NOTE]
> ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。 ユーザー アカウントを一時的に無効にする場合は [、「Skype for Business Server](user-accounts.md#Disable)で以前に有効にしたユーザー アカウントを無効または再び有効にする」を参照してください。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. 表で、削除するユーザー アカウントをクリックします。

6. [**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。

7. ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用してユーザー アカウントを削除する

このコマンドレットを使用して、ユーザー アカウントDisable-CsUserできます。 このコマンドレットは、Skype for Business Server 管理シェルまたはリモート セッション サーバーから実行Windows PowerShell。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。 プロセスは Skype for Business Server でも同じです。

### <a name="to-remove-a-user-account"></a>ユーザー アカウントを削除するには
ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。 次に例を示します。

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

詳細については [、Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。

## <a name="see-also"></a>関連項目
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
