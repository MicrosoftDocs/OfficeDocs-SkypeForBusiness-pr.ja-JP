---
title: アドレス帳を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通常、アドレス帳は他のトポロジと一緒に移行されます。 ただし、従来の環境で次のようにカスタマイズした場合は、移行後の手順を実行する必要があります。
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752839"
---
# <a name="migrate-address-book"></a>アドレス帳を移行する

通常、アドレス帳は他のトポロジと一緒に移行されます。 ただし、従来の環境で次のようにカスタマイズした場合は、移行後の手順を実行する必要があります。 

- アドレス帳の正規化ルールをカスタマイズした場合。

- **UseNormalizationRules** の既定の値を False に変更した場合。 


 **アドレス帳の正規化ルール**

従来の環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。 アドレス帳の正規化ルールをカスタマイズしていない場合は、アドレス帳サービスで移行するものは何もありません。 Skype for Business Server 2019 の既定の正規化ルールは、従来のインストールの既定のルールと同じです。 カスタマイズした正規化ルールを移行するには、このセクションの後半の手順に従います。

> [!NOTE]
> 組織でリモート通話コントロールを使用していて、アドレス帳の正規化ルールをカスタマイズした場合は、リモート通話コントロールを使う前に、このトピックの手順を遂行しなければなりません。この手順では、RTCUniversalServerAdmins グループのメンバーシップまたはそれに相当する権限が必要です。 

 **False に設定した UseNormalizationRules**

**UseNormalizationRules**の値を False に設定して、ユーザーが Skype For business Server 2019 を使用せずに Active Directory ドメインサービスで定義された電話番号を使用できるようにする場合は、 **UseNormalizationRules**および**Ignoregenericrules**パラメーターを True に設定する必要があります。 これらのパラメーターを True に設定するには、このセクションの後半の手順に従います。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>アドレス帳のカスタマイズした正規化ルールを移行するには

1. アドレス帳の共有フォルダーのルートにある Company_Phone_Number_Normalization_Rules.txt ファイルを検索し、Skype for Business Server 2019 パイロットプールのアドレス帳共有フォルダーのルートにコピーします。

    > [!NOTE]
    > アドレス帳の正規化ルールの例は、ABS Web コンポーネントのファイルディレクトリにインストールされています。 パスは **$installedDriveLetter: Files\Files\/Skype For Business Server 2019 \ Web Components\Address Book Sample_Company_Phone_Number_Normalization_Rules.txt**。 このファイルは、アドレス帳の共有フォルダーのルートディレクトリに、 **Company_Phone_Number_Normalization_Rules.txt**としてコピーしたり名前を変更したりできます。 たとえば、アドレス帳が **$serverX**で共有されている場合、このパスは** \\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**のようになります。 

2. メモ帳などのテキスト エディターを使用して、Company_Phone_Number_Normalization_Rules.txt ファイルを開きます。

3. 特定の種類のエントリは、Skype for Business Server 2019 では正しく動作しません。 このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。

    必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    次の文字列では正規化ルールに問題は生じません。

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules および IgnoreGenericRules を true に設定するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. 次のいずれかの操作を行います。

   - 展開に Skype for Business Server 2019 のみが含まれている場合は、グローバルレベルで次のコマンドレットを実行して、 **UseNormalizationRules**および**ignoregenericrules**の値を True に変更します。 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 展開に Skype for Business Server 2019 と従来のインストールの組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジ内の各 Skype for Business Server 2019 プールに割り当てます。

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. 中央管理ストアのレプリケーションがすべてのプールで実行されるのを待ちます。

4. 展開の電話正規化ルール ファイル "Company_Phone_Number_Normalization_Rules.txt" を変更し、コンテンツをクリアします。 このファイルは、各 Skype for Business Server 2019 プールのファイル共有にあります。 ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules.txt" という名前の空のファイルを作成します。

5. すべてのフロントエンドプールが新しいファイルを読み取るまで数分待機します。

6. 展開の各 Skype for Business Server 2019 プールで次のコマンドレットを実行します。

   ```PowerShell
   Update-CsAddressBook
   ```


