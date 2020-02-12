---
title: アドレス帳の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 通常、アドレス帳は、他のトポロジと共に移行されます。 ただし、従来の環境で次のようにカスタマイズした場合は、移行後のいくつかの手順を実行する必要がある場合があります。
ms.openlocfilehash: 976717679a5a2f1dbdd1e2045cc5d5dfe43911e3
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888166"
---
# <a name="migrate-address-book"></a>アドレス帳の移行

通常、アドレス帳は、他のトポロジと共に移行されます。 ただし、従来の環境で次のようにカスタマイズした場合は、移行後のいくつかの手順を実行する必要がある場合があります。 

- アドレス帳の正規化規則をカスタマイズします。

- **UseNormalizationRules**パラメーターの既定値が False に変更されました。 


 **アドレス帳正規化ルール**

従来の環境でアドレス帳の正規化ルールをカスタマイズした場合は、カスタマイズしたルールをパイロットプールに移行する必要があります。 アドレス帳の正規化ルールをカスタマイズしていない場合、アドレス帳サービスに移行することはできません。 Skype for Business Server 2019 の既定の正規化ルールは、従来のインストールの既定の規則と同じです。 カスタマイズされた正規化ルールを移行するには、このセクションの後半の手順を実行します。

> [!NOTE]
> 組織でリモート通話コントロールを使用していて、アドレス帳正規化ルールをカスタマイズしている場合、リモート通話コントロールを使用する前に、このトピックの手順を実行する必要があります。 この手順では、RTCUniversalServerAdmins グループのメンバーシップ、または同等の権限が必要です。 

 **UseNormalizationRules が False に設定**

ユーザーが Skype for Business Server 2019 で正規化ルールを適用せずに Active Directory ドメインサービスで定義されているように、 **UseNormalizationRules**の値を False に設定した場合、 **UseNormalizationRules**と**Ignoregenericrules**パラメーターを True に設定する必要があります。 このセクションの後半の手順に従って、これらのパラメーターを True に設定します。 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>アドレス帳のカスタマイズされた正規化ルールを移行するには

1. アドレス帳の共有フォルダーのルートで Company_Phone_Number_Normalization_Rules .txt ファイルを見つけて、Skype for Business Server 2019 パイロットプールのアドレス帳の共有フォルダーのルートにコピーします。

    > [!NOTE]
    > サンプルのアドレス帳の正規化ルールは、ABS Web コンポーネントファイルディレクトリにインストールされています。 パスは **$installedDriveLetter です。 Skype For Business Server 2019 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt**をご覧ください。 このファイルは、アドレス帳の共有フォルダーのルートディレクトリに**Company_Phone_Number_Normalization_Rules .txt**としてコピーし、名前を変更することができます。 たとえば、 **$serverX**で共有されているアドレス帳は、 ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**のようなパスになります。 

2. メモ帳などのテキストエディターを使用して、Company_Phone_Number_Normalization_Rules .txt ファイルを開きます。

3. 一部の種類のエントリは、Skype for Business Server 2019 では正しく動作しません。 この手順で説明したエントリの種類をファイルで確認し、必要に応じて編集して、変更内容をパイロットプールのアドレス帳の共有フォルダーに保存します。

    必要な空白または句読点を含む文字列は、正規化ルールに入力された文字列から削除されるため、正規化ルールが失敗します。 文字列に必要な空白または句読点が含まれている場合は、文字列を変更する必要があります。 たとえば、次の文字列では正規化ルールが失敗します。

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    次の文字列では、正規化ルールが失敗することはありません。

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules と IgnoreGenericRules を true に設定するには

1. Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. 次のいずれかを実行します。

   - 展開に Skype for Business Server 2019 のみが含まれている場合は、次のコマンドレットをグローバルレベルで実行して、 **UseNormalizationRules**と**ignoregenericrules**の値を True に変更します。 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - 展開に Skype for Business Server 2019 とレガシインストールの組み合わせが含まれている場合は、次のコマンドレットを実行して、トポロジの各 Skype for Business Server 2019 プールに割り当てます。

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. すべてのプールで一元管理ストアのレプリケーションが実行されるのを待ちます。

4. 展開でコンテンツをクリアするために、電話の正規化規則ファイル "Company_Phone_Number_Normalization_Rules .txt" を変更します。 ファイルは、各 Skype for Business Server 2019 プールのファイル共有にあります。 ファイルが存在しない場合は、"Company_Phone_Number_Normalization_Rules .txt" という名前の空のファイルを作成します。

5. すべてのフロントエンドプールが新しいファイルを読み取るまで数分待ちます。

6. 展開されている各 Skype for Business Server 2019 プールで、次のコマンドレットを実行します。

   ```PowerShell
   Update-CsAddressBook
   ```


