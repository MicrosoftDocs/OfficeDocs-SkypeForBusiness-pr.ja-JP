---
title: Microsoft Teams Rooms の回復ツールを使用する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection: M365-voice
localization_priority: Normal
description: この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。
ms.openlocfilehash: 90e6db7739a4a95e3f1fbde62f5b8dd8bde9e237
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427989"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>Microsoft Teams Rooms の回復ツールを使用する
 
この記事では、Microsoft Teams 室の回復ツールの使用方法について説明します。この機能は、サポートされている状態にシステムを移行するために使用します。 このツールは、Microsoft Teams の [会議室] コンソールに "システム構成の終了" というエラーが表示されている場合に使用します。
  

<a name="Prerequisites"> </a>  
## <a name="prerequisites"></a>前提条件

最新の[Microsoft Teams ルームインストールパッケージ](https://go.microsoft.com/fwlink/?linkid=851168)をダウンロードし、それを USB メモリスティックまたは Microsoft teams 室デバイスにアクセスできるネットワーク共有に抽出します。

また、 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールする必要があります。

<a name="Windows-ver"> </a>
## <a name="verify-windows-version"></a>Windows のバージョンを確認する 

1. [設定> Windows の設定] に移動して、管理者アカウントにログインします。 Microsoft Teams 室のデバイスから**管理者によるサインインを>** します。 このオプションでは、ログイン画面が表示されます。
2. 既定の管理者アカウントであるパスワード`admin` `sfb`を使って、管理者アカウントにサインインします。
3. [スタート] メニューをクリックし`winver.exe`て、検索ボックスに入力し、結果に対して [**実行]* をクリックします。
4. [情報] ウィンドウの2行目の [バージョン] の後の番号をメモしておきます。

>[!NOTE]
>表示されているバージョンが1607以前の場合は、「回復<a href="#Windows-up">前に Windows を更新</a>する」の手順に従って、Proceding を<a href="#Perform">実行</a>してください。 表示されているバージョンが1607よりも大きい場合は、「<a href="#Perform">回復を実行する</a>」の手順に従ってください。

<a name="Windows-up"> </a>
## <a name="update-windows-before-recovery-if-needed"></a>回復前に Windows を更新する (必要な場合)

1. 引き続き管理者ユーザーとしてログインしている場合は、管理者特権の Powershell プロンプトを起動します。
2. コマンド`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`を実行します。
3. Windows Update を実行して、Windows 1709 用の更新プログラムをインストールします。
4. 1709への更新が完了したら、管理者アカウントにサインインし直して、 [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)をインストールします。 更新は、リンクから、または Windows Update を使用して行うことができます。
5. オプションの手順として、Windows Update から入手できる追加の更新プログラムをインストールします。

<a name="Perform"> </a>
## <a name="perform-a-recovery"></a>回復を実行する

1. Microsoft Teams 室のデバイスで管理者アカウントにサインインして、管理者特権のコマンドプロンプトを起動します。
2. Microsoft teams 室のインストールパッケージから抽出されたファイルに含ま`RecoveryTool.ps1`れているファイルにアクセスできる、microsoft Teams のルームデバイスから確認します。 キットは、前提条件を準備するときに使用したネットワーク共有または USB ドライブにあります。
3. Powershell .exe コマンド`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`を実行します。
4. スクリプト選択オプション`1:"Repair System"`のプロンプトが表示された場合。
5. 完了したら、Microsoft Teams 室のデバイスを再起動します。 自動的に再起動され、2回目の回復が完了します。



<a name="See"> </a>  
## <a name="see-also"></a>関連項目
 
[Microsoft Teams Rooms ヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
