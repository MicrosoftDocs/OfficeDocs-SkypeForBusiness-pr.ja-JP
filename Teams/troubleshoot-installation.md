---
title: Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Windows の Teams デスクトップ クライアント アプリのインストールと更新に関する問題をトラブルシューティングする方法について説明します。
ms.openlocfilehash: 4183a04458147e63f8168f703bf16682b3bea9e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804557"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング

この記事では、Windows で実行されている Teams デスクトップ クライアント アプリのインストールと更新に関する問題を診断し、トラブルシューティングする方法について説明します。

## <a name="check-whether-teams-is-updated-successfully"></a>Teams が正常に更新されているかどうかを確認する

以下の手順に従って、Teams の更新が正常にインストールされているかどうかを確認します。

1. Teams で、プロファイルの画像を選択してから、**[概要]** > **[バージョン]** をクリックします。
2. 同じメニューで、[**更新プログラムのチェック**] をクリックします。
3. アプリの上部にあるバナーが、Teams の「更新」が必要であることを示すのを待ちます。 このプロセスにより、新しいバージョンの Teams がダウンロードされると、リンクは約 1 分後に表示されます。 また、既に最新バージョンを実行しているかどうかをバナーで確認することもできます。その場合、更新は必要ありません。
4. バナーの [更新] リンクをクリックします。
5. Teams が再起動するまで待ってから、手順 1 を繰り返して、アプリが更新されているかどうかを確認します。

失敗メッセージが表示される場合、または、バージョン番号が手順 4 と同じである場合は、更新プロセスに失敗しています。

## <a name="troubleshoot-installation-and-update-issues"></a>インストールと更新に関する問題のトラブルシューティング

### <a name="troubleshoot-installation-issues"></a>インストールに関する問題のトラブルシューティング

Teams がインストールされている場合、Teams インストーラーは一連のイベントを %LocalAppData%\SquirrelTemp\SquirrelSetup.log に記録します。 最初に調べる必要があるのは、ログの最後にあるエラー メッセージまたはコール スタックです。 ログの先頭にあるコール スタックは、インストールの問題が存在することを意味しない場合があることに注意してください。 必要なものを確認するために、(別のコンピューターであっても) 正常なインストールのログとログを比較する方が簡単です。

SquirrelSetup.log に原因が示されていない場合、または問題のトラブルシューティングを行うための詳細情報が必要な場合は、「[アプリケーションとシステム ログを収集して分析する](#collect-and-analyze-application-and-system-logs)」を参照してください。

### <a name="troubleshoot-update-issues"></a>更新に関する問題のトラブルシューティング

Teams が正常にインストールされると、ログの場所が %LocalAppData%\SquirrelTemp から %LocalAppData%\Microsoft\Teams に切り替わります。 この場所には、SquirrelSetup.log と logs.txt の 2 つのログ ファイルがあります。

- この場所にある SquirrelSetup.log ファイルは、Teams アプリにサービスを提供する実行可能ファイルである Update.exe によって書き込まれます。
- Logs.txt ファイルは、重要なアプリケーション イベントを記録するために Teams アプリ (具体的には Teams.exe) によって使用されます。 失敗情報が含まれている可能性があります。

これらのログ ファイルには、個人を特定できる情報 (PII) が含まれているため、Microsoft には送信されません。

Teams は、(ポリシーに応じて) 更新プロセスを自動的に開始することができます。または、ユーザーのプロファイル画像 > **[更新プログラムのチェック]** に移動して、手動で更新を確認できます。 いずれの方法でも、次のイベント シーケンスを使用します。

1. **更新プログラムのチェック**。 Teams は Web 要求を行い、現在のアプリのバージョンと展開リング情報を含めます。 この手順の目標は、ダウンロード リンクを取得することです。 この手順での失敗は、Logs.txt に記録されます。
2. **更新プログラムのダウンロード**。 Teams は、手順 1 で取得したダウンロード リンクを使用して、更新プログラムをダウンロードします。 ダウンロードが完了すると、Teams は Update.exe を呼び出してダウンロードをステージングします。 また、ダウンロード失敗は、Logs.txt に記録されます。
3. **更新プログラムをステージングする**。 ダウンロードされたコンテンツは検証され、中間フォルダー %LocalAppData%\Microsoft\Teams\stage) に解凍され、Update.exe によって実行されます。 この段階での失敗は SquirrelTemp.log に記録されます。
4. **更新プログラムのインストール**。 Teams を開始する方法はいくつかあります。 ユーザーがログインすると、システムが自動的に Teams を開始します。または、ショートカットを使用して Teams を開始することもできます。 この手順では、Update.exe がステージング フォルダーの存在を確認し、コンテンツを再度検証し、ファイル操作を実行してアプリのステージングを解除します。 %LocalAppData%\Microsoft\Teams\current の古いアプリケーション フォルダーは %LocalAppData%\Microsoft\Teams\previous にバックアップされ、ステージ フォルダーの名前は "current" に変更されます。 この段階での失敗は SquirrelTemp.log に記録されます。

SquirrelTemp.log または Logs.txt には、根本的な原因を特定するのに十分な情報が含まれていないため、問題のトラブルシューティングを行うための詳細情報が必要な場合は、[アプリケーションおよびシステム ログの収集と分析](#collect-and-analyze-application-and-system-logs)に進みます。

## <a name="collect-and-analyze-application-and-system-logs"></a>アプリケーションおよびシステム ログの収集と分析

このセクションでは、アプリケーションとシステムのログを収集して分析し、問題のトラブルシューティングを行うためのより包括的な情報を取得する方法について説明します。 Sysinternals ツールを使用して、これらの手順を完了します。 詳細については、「[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)」を参照してください。

### <a name="collect-logs"></a>ログを収集する

1. [Sysinternals tools](https://download.sysinternals.com/files/SysinternalsSuite.zip) をダウンロードします。
2. ローカルドライブの %TEMP% フォルダーに zip ファイルを展開します。
3. 管理者特権でのコマンド プロンプトを開き、次の操作を実行します。

    1. 次のコマンドを実行して、TEMP フォルダーに移動します。

        ```console
        cd /d %TEMP%
        ```
    2. 設定とアプリケーション ログをコピーします。 障害点によっては、これらのログの一部が存在しない場合があります。

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 次のコマンドを実行して、開いているハンドルをキャプチャします。

        ```console
        handle > handles.txt
        ```

    4. 次のコマンドを実行して、開いている DLL をキャプチャします。

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. 次のコマンドを実行して、実行中のドライバーをキャプチャします。

        ```console
        driverquery /v > driverquery.txt
        ```

    6. 次のコマンドを実行して、Teams フォルダーのアクセス制御リスト (ACL) をキャプチャします。

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>ログの分析 (上級ユーザー向け)

更新に失敗すると、アプリが予期しない動作をする可能性があります。 たとえば、Teams を終了できない、古いバージョンの Teams を使用している、または Teams を開始できないなどです。 更新中に問題が発生した場合は、原因を見つけるために最初に探す場所は SquirrelTemp.log です。 ここでは、最も一般的なものから最も一般的でないものまで、さまざまな種類の更新の失敗と、ログを使用してそれらを分析およびトラブルシューティングする方法を示します。

#### <a name="unable-to-exit-teams"></a>Teams を終了できません

Teams は自身を新しいバージョンに更新する必要があると判断すると、新しいアプリをダウンロードしてステージングし、次にコンピューターがアイドル状態になったときに自動的に再起動する機会を待ちます。 このプロセス中の一般的な問題は、別のプロセスやファイル システム ドライバーが Teams.exe プロセスをロックして、Teams.exe が終了しない場合です。 その結果、Teams アプリは、新しくダウンロードされてステージングされたアプリに置き換えることはできません。

トラブルシューティングのヒント:

- これが発生している問題であることを確認するために、Teams を終了します (タスクバーの [Teams] を右クリックし、[**終了**] をクリックします)。 次に、Windows のタスク マネージャーを開いて、Teams インスタンスがまだ実行中であるかどうかを確認します。  
- この問題が発生しているコンピューターを使用していない場合は、この問題が発生しているコンピューターから収集された SquirrelTemp.log を調べ、"Program: Unable to terminate the process in the log" というエントリを探します。
- Teams.exe の終了を妨げている原因を特定するには、Dlls.txt および Handles.txt ログを確認します。 これらは、Teams の終了を妨げたプロセスを示しています。
- Teams の終了を妨げる可能性のあるもう 1 つの原因は、カーネル モードのファイル システム フィルター ドライバーです。 SysInternals ツールの [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump) を使用して、```procdump -mk <pid>``` を実行して、カーネル モード プロセス ダンプを収集します。ここで、<pid> はタスク マネージャーから取得したプロセス ID です。 Driverquery.txt ログファイルを調べて、Teams に干渉する可能性のあるアクティブなフィルター ドライバーを確認することもできます。
- この状態から回復するには、コンピューターを再起動します。

#### <a name="file-permissions"></a>ファイルのアクセス許可

Teams は、インストールおよび更新プロセスを通して、ユーザーのプロファイルに多くのサブフォルダーとファイルを作成します。 アプリとアップデーターは昇格されていないユーザーとして実行されるので、次のフォルダーに対する読み取りアクセス許可と書き込みアクセス許可を付与する必要があります。

|フォルダー  |使用元  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | インストール段階での Teams (たとえば、Teams_Windows_x64.exe)        |
|%LocalAppData%\Microsoft\Teams  | 更新プロセス中にアプリ パッケージを抽出してステージングする Teams アップデーター (Update.exe)        |
|%AppData%\Microsoft\Teams   |  Teams アプリ (Teams.exe) は、設定、アプリの状態、(事前にステージングされた) ダウンロードした更新パッケージを保存します       |

Teams がファイルに書き込めないため、アクセスが拒否された場合、別のソフトウェア アプリケーションが干渉しているか、セキュリティ記述子のエントリがフォルダーへの書き込みアクセスを制限している可能性があります。

トラブルシューティングのヒント:

- SquirrelTemp.log または Logs.txt で「アクセスが拒否されました」の証拠を探します。 これらのファイルを確認して、失敗したファイルへの書き込みが試みられているかどうかを確認します。
- Icacls.txt を開き、管理者以外のユーザーによる書き込み操作をブロックする効果的なアクセス制御エントリ (ACE) を探します。通常は、DACL エントリのいずれかになります。 詳細については、[icacls のドキュメント](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)を参照してください。

#### <a name="file-corrupted"></a>ファイルの破損

場合によっては、暗号化ソフトウェアが %LocalAppData%\Microsoft\Teams フォルダー内のファイルを変更する可能性があり、これにより Teams が起動できなくなる可能性があります。 アプリが更新されていないときでも、いつでも発生する可能性があります。 残念ながら、ファイルが破損している場合、この状態から回復する唯一の方法は、Teams をアンインストールして再インストールすることです。

> [!NOTE]
> これらの手順のいずれかを使用しても問題の根本的な原因を特定できない場合は、[プロセス モニター](https://docs.microsoft.com/sysinternals/downloads/procmon) セッションを試すことをお勧めします。 プロセス モニターは、レジストリやファイルシステムへのアクセスを記録する Sysinternals ツールです。

## <a name="related-topics"></a>関連項目

- [Teams のクライアントを取得する](get-clients.md)
- [Teams クライアントの更新プログラム](teams-client-update.md)
- [Teams のトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
