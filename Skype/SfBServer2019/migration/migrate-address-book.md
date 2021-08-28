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
ms.localizationpriority: medium
description: 一般に、アドレス帳は他のトポロジと共に移行されます。 ただし、従来の環境で次の手順をカスタマイズした場合は、移行後の手順を実行する必要がある場合があります。
ms.openlocfilehash: 0ef965ef67393604e257049681a64ffb3c5b8fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599722"
---
# <a name="migrate-address-book"></a>アドレス帳の移行

一般に、アドレス帳は他のトポロジと共に移行されます。 ただし、従来の環境で次の手順をカスタマイズした場合は、移行後の手順を実行する必要がある場合があります。 

- アドレス帳の正規化ルールをカスタマイズした場合。

- **UseNormalizationRules** の既定の値を False に変更した場合。 


 **アドレス帳の正規化ルール**

従来の環境でアドレス帳正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロット プールに移行する必要があります。 アドレス帳の正規化ルールをカスタマイズしていない場合は、アドレス帳サービスで移行するものは何もありません。 2019 Skype for Business Serverの既定の正規化ルールは、従来のインストールの既定のルールと同じです。 カスタマイズした正規化ルールを移行するには、このセクションの後半の手順に従います。

> [!NOTE]
> 組織でリモート通話コントロールを使用していて、アドレス帳の正規化ルールをカスタマイズした場合は、リモート通話コントロールを使う前に、このトピックの手順を遂行しなければなりません。この手順では、RTCUniversalServerAdmins グループのメンバーシップまたはそれに相当する権限が必要です。 

 **False に設定した UseNormalizationRules**

**UseNormalizationRules** の値を False に設定すると、ユーザーは、Skype for Business Server 2019 年の正規化ルールを適用せずに Active Directory ドメイン サービスで定義されている電話番号を使用できます **。UseNormalizationRules** パラメーターと **IgnoreGenericRules** パラメーターを True に設定する必要があります。 これらのパラメーターを True に設定するには、このセクションの後半の手順に従います。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>アドレス帳のカスタマイズした正規化ルールを移行するには

1. アドレス帳Company_Phone_Number_Normalization_Rules.txtのルートにあるファイルを見つけ、2019 年のパイロット プール内のアドレス帳共有フォルダーのルートにコピー Skype for Business Serverします。

    > [!NOTE]
    > サンプルのアドレス帳正規化ルールが ABS Web コンポーネント ファイル ディレクトリにインストールされています。 パスは **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web コンポーネント\アドレス帳ファイル\Files\** Sample_Company_Phone_Number_Normalization_Rules.txtです。 このファイルは、アドレス帳共有フォルダー **Company_Phone_Number_Normalization_Rules.txtディレクトリに** コピーして名前を変更できます。 **たとえば、$serverX** で共有されるアドレス帳のパスは **\\ 、$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles** に似ています。 

2. メモ帳などのテキスト エディターを使用して、Company_Phone_Number_Normalization_Rules.txt ファイルを開きます。

3. 2019 年中に特定の種類のエントリがSkype for Business Server。 このファイルに目を通して、このステップで説明しているような種類のエントリがあれば、必要に応じてそれを編修し、パイロット プール内のアドレス帳共有フォルダーに変更後のファイルを保存します。

    必要な空白文字や区切り文字が文字列に含まれていると、正規化ルールが正常に機能しなくなります。これらの文字は、正規化ルールに入力される文字列から取り除かれるためです。必要な空白文字や区切り文字が含まれる文字列を使用する場合は、文字列を編集する必要があります。たとえば、次の文字列を使用すると、正規化ルールが正常に機能しません。

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    次の文字列では正規化ルールに問題は生じません。

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules および IgnoreGenericRules を true に設定するには

1. 管理シェルをSkype for Business Serverする: [スタート] をクリックし、[すべてのプログラム] をクリックし、[Microsoft Skype for Business Server **2019]** をクリックし、[管理シェルSkype for Business Server **クリックします**。

2. 次のいずれかの操作を行います。

   - 展開に 2019 Skype for Business Serverのみを含む場合は、グローバル レベルで次のコマンドレットを実行して **、UseNormalizationRules** と **IgnoreGenericRules** の値を True に変更します。 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 展開に Skype for Business Server 2019 と従来のインストールの組み合わせが含まれる場合は、次のコマンドレットを実行し、トポロジ内の Skype for Business Server 2019 プールに割り当てる必要があります。

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. すべてのプールでサーバーの全体管理ストアのレプリケーションが発生するのを待ちます。

4. 展開の電話正規化ルール ファイル "Company_Phone_Number_Normalization_Rules.txt" を変更し、コンテンツをクリアします。 ファイルは、2019 年の各プールSkype for Business Server共有されます。 ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules.txt" という名前の空のファイルを作成します。

5. すべてのフロントエンド プールが新しいファイルを読み取るのを数分待ちます。

6. 展開内の各 2019 プールSkype for Business Server次のコマンドレットを実行します。

   ```PowerShell
   Update-CsAddressBook
   ```


