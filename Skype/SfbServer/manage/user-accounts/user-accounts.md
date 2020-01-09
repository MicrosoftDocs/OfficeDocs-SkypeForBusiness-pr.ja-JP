---
title: Skype for Business Server のユーザーアカウントを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事のセクションでは、Skype for Business Server の Active Directory ユーザーを有効にしたり、一時的に無効にしたり、削除したりする方法について説明します。
ms.openlocfilehash: 45217593dd010c4daf73d6b5edcbf6f5f4e681a5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992404"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Skype for Business Server のユーザーアカウントを管理する

この記事のセクションでは、Skype for Business Server の Active Directory ユーザーを有効にしたり、一時的に無効にしたり、削除したりする方法について説明します。

Active Directory ユーザーを有効にする方法については、「[新しいユーザーアカウントを作成](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)する」を参照してください。 Active Directory ユーザーを削除する方法については、「[ユーザーアカウントを削除](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)する」を参照してください。

以下の手順は、Skype for Business の使用が最も低い場合にメンテナンスウィンドウで実行する必要があります。 このスケジュールが毎日または毎週のどちらで実行されるかは、組織のニーズによって決まります。

この記事では、次の手順について説明します。

- [1人以上のユーザーを検索するには](user-accounts.md#Search)

- [新しい Skype for Business Server ユーザーを追加して有効にする](user-accounts.md#Add)

- [Skype for Business Server で既に有効になっていたユーザーアカウントを無効にするか、再び有効にする](user-accounts.md#Disable)

- [エンタープライズ Voip のユーザーを無効にする](user-accounts.md#Disable_EV)

- [Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>1人以上のユーザーを検索するには
<a name="Search"> </a>

検索クエリの結果を使用して、Skype for Business Server の Active Directory ユーザーを構成することができます。 ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。

ユーザーを検索するには、[Skype for Business Server] コントロールパネルまたは [Active Directory ユーザーとコンピューター] スナップインを使用します。 次の手順では、Skype for Business Server コントロールパネルを使用してユーザーを検索する方法について説明します。

> [!NOTE]
> 中央フォレストトポロジを持つ環境では、ユーザーのメールアドレスでユーザーを検索すると、検索結果が正確でない場合があります。 代わりに、SIP アドレスプレフィックスを指定してユーザーを検索することもできます。たとえば、sip: name、検索フィルターを追加して、メールアドレスの一部を含む SIP アドレスを選ぶか、または、**ユーザー**コマンドレットを使用します。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、検索するユーザーアカウントの表示名、姓、名、SAM アカウント名、SIP アドレス、またはライン URI のすべてまたは最初の部分を入力して、[**検索**] をクリックします。

5. (オプション) 結果を絞り込むための追加の検索条件を次のように指定します。

   a. **検索結果**の上にある画面の右上隅にある展開矢印ボタンをクリックし、[**フィルターの追加**] をクリックします。

   b. [ユーザー] プロパティを入力するか、ドロップダウンリストの矢印をクリックして、ユーザープロパティを選択します。

   c. [指定の**値**に等しい] または [指定の**値に等しい**] を**クリックします**。

   d. 検索結果をフィルター処理するために使用する検索条件をテキストボックスに入力し、[**検索**] をクリックします。

6. 検索結果が [**検索結果**] の下に表示されます。 リスト内の任意またはすべてのユーザーを選択し、選択したユーザーに対して構成タスクを実行することができます。

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>新しい Skype for Business Server ユーザーを追加して有効にする
<a name="Add"> </a>

Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後は、skype for business server コントロールパネルを使用して、Active Directory ユーザーを Skype for Business Server に追加することで、新しい Skype for business server のユーザーアカウントを作成して有効にすることができます。

コマンドレットを使用することもできます。特[に、CsUser を有効に](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)することもできます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーを有効にする] を**クリックします。

5. [**新しい Lync Server ユーザー** ] ダイアログボックスで、[**追加**] をクリックします。

6. [**ユーザーの検索**] ボックスで、名前、表示名、姓、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、メールアドレス、ユーザープリンシパル名 (UPN)、または必要な Active Directory ユーザーアカウントの電話番号のすべてまたは最初の部分を入力し、[**検索**] をクリックします。

7. 表で、Skype for Business Server に追加するアカウントを選び、[ **OK**] をクリックします。

8. プールにユーザーを割り当て、追加の詳細を指定して、ポリシーを目的のユーザーに割り当て、[**有効に**する] をクリックします。

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Skype for Business Server で既に有効になっていたユーザーアカウントを無効にするか、再び有効にする
<a name="Disable"> </a>

次の手順を使用して、ユーザーアカウント用に構成した Skype for business Server の設定を失わずに、Skype for Business Server で事前に有効になっているユーザーアカウントを無効にすることができます。 Skype for Business Server のユーザーアカウント設定が失われないため、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再び有効にすることができます。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスで、無効または再度有効にするユーザーアカウントの表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または行の Uniform resource IDENTIFIER (URI) のすべてまたは最初の部分を入力して、[**検索**] をクリックします。

5. 表で、無効にする、またはもう一度有効にするユーザーアカウントをクリックします。

6. [**アクション**] メニューで、次のいずれかの操作を行います。

   - Skype for Business Server のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。

   - Skype for Business Server のユーザーアカウントを有効にするには、[ **Lync server のために再度有効**にする] をクリックします。

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Windows Powershell を使用して、ユーザーアカウントを無効にするか、再び有効にする

ユーザーアカウントは一時的に無効にすることができます。また、**設定-CsUser**コマンドレットを使用して、後で再び有効にすることができます。 このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。

### <a name="to-disable-a-user-account"></a>ユーザーアカウントを無効にするには

- ユーザーアカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。 次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>ユーザーアカウントを再度有効にするには

- 無効のユーザーアカウントを再び有効にするには、Enabled プロパティの値を True ($True) に設定します。 次に例を示します。

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。

## <a name="disable-a-user-for-enterprise-voice"></a>エンタープライズ Voip のユーザーを無効にする
<a name="Disable_EV"> </a>

Skype for Business Server を有効にしているユーザーアカウントのエンタープライズ Voip を無効にするには、次の手順を使用します。

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>エンタープライズ Voip のユーザーアカウントを無効にするには

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。

5. 表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。

6. [**編集**] メニューの [**詳細の表示**] をクリックします。

7. [ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] 以外のオプションをクリックします。

    > [!NOTE]
    > ユーザーが Lync を使って音声またはビデオ通話を発信することを制限するには、[**テレフォニー**] で [**オーディオ/ビデオを無効**にする] をクリックします。

8. [**コミット**] をクリックします。

これで、ユーザーはエンタープライズ Voip 機能を使用できなくなります。 関連情報: <br/>[エンタープライズ音声とモバイル機能](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Skype for Business Server でエンタープライズ Voip のユーザーを有効にする](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server 管理シェル](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する
<a name="Remove"> </a>

Skype for Business Server で以前に追加したユーザーアカウントを削除するには、次の手順に従います。

> [!NOTE]
> ユーザーを削除すると、ユーザーアカウントに対して構成した設定が失われます。 代わりに、ユーザーアカウントを一時的に無効にする場合は、「 [Skype For Business Server 用に有効になっていたユーザーアカウントを無効にする、またはもう一度有効](user-accounts.md#Disable)にする」を参照してください。

1. CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2. ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**ユーザー**] をクリックします。

4. [**ユーザーの検索**] ボックスで、無効または再度有効にするユーザーアカウントの表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または行の Uniform resource IDENTIFIER (URI) のすべてまたは最初の部分を入力して、[**検索**] をクリックします。

5. テーブルで、削除するユーザーアカウントをクリックします。

6. [**操作**] メニューの [ **Lync Server から削除**] を選択すると、ダイアログボックスが表示されます。

7. ダイアログボックスで、[ **OK** ] を選択してユーザーを削除します。

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Windows Powershell コマンドレットを使用してユーザーアカウントを削除する

ユーザーアカウントを削除するには、ユーザーの無効化コマンドレットを使用します。 このコマンドレットは、Skype for Business Server 管理シェルから、またはリモートセッション Windows PowerShell から実行できます。 リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。 このプロセスは、Skype for Business Server でも同じです。

### <a name="to-remove-a-user-account"></a>ユーザーアカウントを削除するには
ユーザーアカウントを削除するには、ユーザーの無効化コマンドレットを使用します。 次に例を示します。

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

詳細については、「[ユーザーの無効化](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)」コマンドレットのヘルプトピックを参照してください。

## <a name="see-also"></a>関連項目
<a name="Remove"> </a>

[(CsUser) を有効にする](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[無効-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
