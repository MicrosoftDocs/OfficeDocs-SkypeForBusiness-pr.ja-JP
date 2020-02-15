---
title: Skype for Business Server のユーザーアカウントを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事のセクションでは、Skype for Business Server から Active Directory ユーザーを有効または無効にしたり、削除したりする方法について説明します。
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009640"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Skype for Business Server のユーザーアカウントを管理する

この記事のセクションでは、Skype for Business Server から Active Directory ユーザーを有効または無効にしたり、削除したりする方法について説明します。

Active Directory ユーザーを有効にする方法については、「[新しいユーザーアカウントを作成](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)する」を参照してください。 Active Directory ユーザーを削除する方法については、「[ユーザーアカウントを削除](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)する」を参照してください。

これらの手順は、Skype for Business の使用率が低いときに、メンテナンス期間中に実行する必要があります。 これが毎日または毎週のどちらのスケジュールで行われるかは、組織のニーズによって決まります。

この記事には、以下の手順が含まれています。

- [1 つ以上のユーザーを検索するには](user-accounts.md#Search)

- [新しい Skype for Business Server ユーザーを追加して有効にする](user-accounts.md#Add)

- [Skype for Business Server で既に有効になっているユーザーアカウントを無効または再度有効にする](user-accounts.md#Disable)

- [エンタープライズ Voip のユーザーを無効にする](user-accounts.md#Disable_EV)

- [Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>1 つ以上のユーザーを検索するには
<a name="Search"> </a>

検索クエリの結果を使用して、Skype for Business Server の Active Directory ユーザーを構成することができます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。

ユーザーを検索するには、[Skype for Business Server コントロールパネル] または [Active Directory ユーザーとコンピューター] スナップインを使用します。 次の手順では、Skype for Business Server コントロールパネルを使用してユーザーを検索する方法について説明します。

> [!NOTE]
> 中央フォレストトポロジを使用している環境では、ユーザーの電子メールアドレスでユーザーを検索すると、検索結果が正確でないことがあります。 代わりに、SIP アドレスプレフィックスを指定してユーザーを検索できます。たとえば、sip: name、検索フィルターを追加して、電子メールアドレスの一部を含む SIP アドレスを選択するか、または**Get-help user**コマンドレットを使用します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。

   a.  画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。

   b.  ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。

   c. [**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。

   d. テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。

6. [**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>新しい Skype for Business Server ユーザーを追加して有効にする
<a name="Add"> </a>

Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後、skype for Business server コントロールパネルを使用して、Active Directory ユーザーを Skype for Business Server に追加することにより、新しい Skype for business Server ユーザーアカウントを作成して有効にすることができます。

コマンドレットを使用することもできます。具体的には、 [-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)を使用します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。

4. [**ユーザーの有効化**] をクリックします。

5. [**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。

6. [**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

7. 表で、Skype for Business Server に追加するアカウントを選択し、[ **OK]** をクリックします。

8. ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Skype for Business Server で既に有効になっているユーザーアカウントを無効または再度有効にする
<a name="Disable"> </a>

次の手順を使用して、ユーザーアカウントに対して構成した Skype for Business Server の設定を失わずに、Skype for business Server で既に有効になっているユーザーアカウントを無効にすることができます。 Skype for Business Server のユーザーアカウント設定は失われないので、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再度有効にすることができます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。

4. [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. 表で、無効または再度有効にするユーザー アカウントをクリックします。

6. [**アクション**] メニューで、次のいずれかを実行します。

   - Skype for Business Server のユーザーアカウントを一時的に無効にするには、[ **Lync Server に対して一時的に無効**にする] をクリックします。

   - Skype for Business Server のユーザーアカウントを有効にするには、[ **Lync Server の再有効化**] をクリックします。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows Powershell を使用してユーザーアカウントを無効にするか、再度有効にする

ユーザーアカウントを一時的に無効にして**から、ユーザーコマンドレット**を使用して再び有効にすることができます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事[「クイックスタート: Microsoft Lync Server 2010 を使用したリモート PowerShell の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。

### <a name="to-disable-a-user-account"></a>ユーザーアカウントを無効にするには

- ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。 例:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>ユーザーアカウントを再度有効にするには

- 無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。 次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットのヘルプトピックを参照してください。

## <a name="disable-a-user-for-enterprise-voice"></a>エンタープライズ Voip のユーザーを無効にする
<a name="Disable_EV"> </a>

Skype for Business Server が有効になっているユーザーアカウントのエンタープライズ Voip を無効にするには、次の手順を使用します。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを無効にするには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。

4. **[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。

5. 表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。

6. [**編集**] メニューの [**詳細の表示**] をクリックします。

7. [**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。

    > [!NOTE]
    > ユーザーが Lync を使用して音声またはビデオ通話を行うことを制限するには、[**テレフォニー**] で [**音声ビデオを無効**にする] をクリックします。

8. [**確定**] をクリックします。

これで、ユーザーはエンタープライズ Voip 機能を使用できなくなりました。 関連情報: <br/>[エンタープライズ Voip とモビリティ](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Skype for Business Server のエンタープライズ Voip でユーザーを有効にする](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 管理シェル](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する
<a name="Remove"> </a>

Skype for Business Server で以前に追加したユーザーアカウントを削除するには、次の手順を使用します。

> [!NOTE]
> ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。 代わりにユーザーアカウントを一時的に無効にする場合は、「 [Skype For Business Server で既に有効になっているユーザーアカウントの無効化または再有効化](user-accounts.md#Disable)」を参照してください。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで **[ユーザー]** をクリックします。

4. [**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。

5. 表で、削除するユーザー アカウントをクリックします。

6. [**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。

7. ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用してユーザーアカウントを削除する

ユーザーアカウントを削除するには、Disable-CsUser コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルまたはリモートセッション Windows PowerShell から実行できます。 リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事[「クイックスタート: Microsoft Lync Server 2010 を使用したリモート PowerShell の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。

### <a name="to-remove-a-user-account"></a>ユーザーアカウントを削除するには
ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。 次に例を示します。

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

詳細については、「 [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目
<a name="Remove"> </a>

[を有効にする-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[無効-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
