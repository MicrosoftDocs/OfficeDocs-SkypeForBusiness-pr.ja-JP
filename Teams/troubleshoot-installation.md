---
title: Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Windows の Teams デスクトップクライアントアプリのインストールと更新に関する問題のトラブルシューティングを行う方法について説明します。
ms.openlocfilehash: 812beb3471a1d4ee2cbc1e8e7f7b36b2a42e0e2d
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "39920154"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Windows での Microsoft Teams のインストールと更新に関する問題のトラブルシューティング

この記事では、Windows で実行されている Teams デスクトップクライアントアプリのインストールおよび更新に関する問題の診断とトラブルシューティングを行う方法に関するガイダンスを提供します。

## <a name="check-whether-teams-is-updated-successfully"></a>チームが正常に更新されたかどうかを確認する

チームの更新プログラムが正常にインストールされたかどうかを確認するには、次の手順を実行します。

1. Teams で、プロフィール画像を選択し、[バージョン**情報** > ****] をクリックします。
2. 同じメニューで、[**更新プログラムのチェック**] をクリックします。
3. アプリの上部にあるバナーで、チームの "更新" が必要であることを示します。 このプロセスでは、新しいバージョンの Teams がダウンロードされるので、後で1分ほどリンクを表示する必要があります。 また、バナーでは、既に最新バージョンを実行しているかどうかを確認することができます。この場合、更新プログラムは必要ありません。
4. バナーで [更新] リンクをクリックします。
5. Teams が再起動するまで待ってから、手順1を繰り返して、アプリが更新されているかどうかを確認します。

エラーメッセージが表示された場合、または手順4と同じバージョン番号がある場合は、更新処理に失敗しました。

## <a name="troubleshoot-installation-and-update-issues"></a>インストールと更新に関する問題のトラブルシューティング

### <a name="troubleshoot-installation-issues"></a>インストールに関する問題のトラブルシューティング

Teams がインストールされると、Teams installer は%LocalAppData%\SquirrelTemp\SquirrelSetup.log. への一連のイベントをログに記録します。 最初に確認するべきことは、ログの最後にあるエラーメッセージまたはコールスタックです。 ログの最初の呼び出し履歴は、インストールの問題が存在するというわけではないことに注意してください。 必要なものを確認するために、(別のコンピューターでも) インストールが正常に完了した場合でも、ログとログの比較を簡単に行うことができます。

SquirrelSetup で原因が示されない場合、または問題のトラブルシューティングを行うための詳細情報が必要な場合は、「[アプリケーションとシステムログを収集して分析](#collect-and-analyze-application-and-system-logs)する」を参照してください。

### <a name="troubleshoot-update-issues"></a>更新に関する問題のトラブルシューティング

Teams が正常にインストールされると、ログの場所が%LocalAppData%\SquirrelTemp から%AppData%\Microsoft\Teams. に切り替わります。 この場所には、SquirrelSetup と .log という2つのログファイルがあります。

- この場所に SquirrelSetup ファイルが書き込まれます。 update.exe は、Teams アプリをサービスする実行可能ファイルです。
- ログの .txt ファイルは、Teams アプリ (具体的には Teams) によって、重要なアプリケーションイベントを記録するために使用されます。 エラー情報が含まれている可能性があります。

これらのログファイルには、個人を特定できる情報 (PII) が含まれているため、Microsoft に送信されることはありません。

チームは、自動的に更新プロセスを開始するか (ポリシーによって異なります)、ユーザーはプロファイルの写真 > 更新プログラムを**確認**することで、更新プログラムを手動で確認できます。 どちらの方法でも、次のイベントシーケンスが使用されます。

1. **更新プログラムを確認**します。 チームが web 要求を行い、現在のアプリのバージョンと展開リングの情報が含まれます。 この手順の目標は、ダウンロードリンクを取得することです。 この手順で失敗すると、ログに記録されます。
2. **更新プログラムをダウンロード**します。 チームは、手順1で取得したダウンロードリンクを使用して、更新プログラムをダウンロードします。 ダウンロードが完了すると、Teams によって update.exe が呼び出され、ダウンロードがステージされます。 ダウンロードに失敗した場合も、output.txt にログが記録されます。
3. **更新をステージ**します。 ダウンロードしたコンテンツは検証され、%LocalAppData%\Microsoft\Teams\stage の中間フォルダーに展開されます。これは、update.exe によって実行されます。 この手順でのエラーは、SquirrelTemp に記録されます。
4. **更新プログラムをインストール**します。 Teams を開始するには、複数の方法があります。 ユーザーがログインしたとき、またはショートカットを使用してチームを起動したときに、システムによってチームが自動的に開始されます。 この手順では、update.exe でステージングフォルダーの存在を確認し、もう一度コンテンツを検証し、ファイル操作を実行してアプリのステージを解除します。 %LocalAppData%\Microsoft\Teams\current の古いアプリケーションフォルダーは%LocalAppData%\Microsoft\Teams\previous にバックアップされ、stage フォルダー名は "current" に変更されます。 この手順でのエラーは、SquirrelTemp に記録されます。

SquirrelTemp または Logs には、基になる原因を特定するための十分な情報が含まれておらず、問題のトラブルシューティングを行うための詳細情報が必要な場合は、「[アプリケーションとシステムログを収集して分析](#collect-and-analyze-application-and-system-logs)する」を参照してください。

## <a name="collect-and-analyze-application-and-system-logs"></a>アプリケーションとシステムログの収集と分析

このセクションでは、アプリケーションとシステムログを収集して分析する方法について説明します。この問題を解決するための包括的な情報を入手します。 次の手順を実行するには、Sysinternals ツールを使用します。 詳細については、「 [Windows Sysinternals](https://docs.microsoft.com/sysinternals/)」を参照してください。

### <a name="collect-logs"></a>ログを収集する

1. [Sysinternals ツール](https://download.sysinternals.com/files/SysinternalsSuite.zip)をダウンロードします。
2. ローカルドライブの% TEMP% フォルダーに zip ファイルを抽出します。
3. 管理者特権でコマンドプロンプトを開き、次の操作を行います。

    1. TEMP フォルダーに移動するには、次の操作を実行します。

        ```
        cd /d %TEMP%
        ```
    2. セットアップログとアプリケーションログをコピーします。 エラーの原因によっては、これらのログの一部が表示されない場合があることに注意してください。

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 開いているハンドルをキャプチャするには、次を実行します。

        ```
        handle > handles.txt
        ```

    4. 次のように実行して、開いている Dll をキャプチャします。

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. 実行されているドライバーをキャプチャするには、次を実行します。

        ```
        driverquery /v > driverquery.txt
        ```

    6. Teams フォルダーのアクセス制御リスト (Acl) を取得するには、次を実行します。

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>分析ログ (上級ユーザー向け)

更新に失敗すると、アプリの予期しない動作が発生する可能性があります。 たとえば、チームを終了したり、古いバージョンの Teams を使用したり、チームを開始したりすることはできません。 更新時に問題が発生した場合は、最初に原因を特定するための最初の場所は SquirrelTemp です。 ここでは、最も一般的な [最小] から [一般的] までのさまざまな更新エラー、およびログを使用した分析とトラブルシューティングの方法について説明します。

#### <a name="unable-to-exit-teams"></a>チームを終了できません

Teams によって、新しいバージョンに更新する必要があると判断された場合は、新しいアプリをダウンロードしてステージングし、次にコンピューターがアイドル状態になったときに、機会が自動的に再起動されるのを待ちます。 このプロセスで一般的に発生する問題は、別のプロセスまたはファイルシステムドライバーによって Teams の .exe プロセスがロックされた場合です。これにより、Teams は終了できなくなります。 このため、新しくダウンロードされたアプリと段階的に展開されたアプリで Teams アプリを置き換えることはできません。

トラブルシューティングのヒント:

- 発生している問題であることを確認するには、Teams を終了します (タスクバーの [チーム] を右クリックし、[**終了**] をクリックします)。 次に、Windows で [タスクマネージャー] を開いて、Teams のインスタンスがまだ実行されているかどうかを確認します。  
- この問題が発生しているコンピューターを使っていない場合は、この問題が発生しているコンピューターから収集された SquirrelTemp を調べて、"ログのプロセスを終了できません" というエントリを探します。
- Teams の終了を妨げている原因を特定するには、file.txt のログを処理します。 これにより、チームが終了できないプロセスが示されます。
- チームが終了するのを防ぐ別の原因として、カーネルモードのファイルシステムフィルタードライバーがあります。 SysInternals tool、 [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)を使用して、実行```procdump -mk <pid>```することによってカーネルモードのプロセス<pid>ダンプを収集します。ここでは、Task MANAGER から取得したプロセス ID を取得します。 Driverquery ログファイルを調べて、Teams の妨げになる可能性のあるアクティブなフィルタードライバーを確認することもできます。
- この状態から回復するには、コンピューターを再起動してください。

#### <a name="file-permissions"></a>ファイルのアクセス許可

チームは、インストールと更新のプロセス全体を通じて、ユーザーのプロファイルにいくつかのサブフォルダーとファイルを作成します。 アプリとアップデーターは、昇格されていないユーザーとして実行されるため、読み取りと書き込みのアクセス許可は、次のフォルダーで許可されている必要があります。

|]  |使用者  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | インストールフェーズでの Teams インストーラー (Teams_Windows_x64 など)        |
|%LocalAppData%\Microsoft\Teams  | 更新プロセス中にアプリパッケージを抽出してステージングするための Teams アップデーター (update.exe)        |
|%AppData%\Microsoft\Teams   |  設定、アプリの状態、および (段階的に) ダウンロードされた更新パッケージを保存するための teams アプリ (Teams)       |

ファイルに書き込むことができないため、Teams でアクセスが拒否されている場合、別のソフトウェアアプリケーションが妨害しているか、セキュリティ記述子エントリがフォルダーへの書き込みアクセスを制限している可能性があります。

トラブルシューティングのヒント:

- SquirrelTemp または .log で "アクセス拒否" の証拠を探します。 これらのファイルを確認して、失敗したファイルへの書き込みが試みられたかどうかを確認します。
- Icacls.exe を開いて、管理者以外のユーザーによる書き込み操作をブロックする有効なアクセス制御エントリ (ACE) を探します。通常、これは DACL エントリの1つです。 詳細については、「 [icacls.exe のドキュメント](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)」を参照してください。

#### <a name="file-corrupted"></a>ファイルが壊れている

場合によっては、暗号化ソフトウェアによって%LocalAppData%\Microsoft\Teams フォルダー内のファイルが変更されることがあります。これにより、チームの開始を防ぐことができます。 これは、アプリが更新されていないときでも、いつでも発生する可能性があります。 残念ながら、ファイルが破損している場合、この状態から回復するには、Teams をアンインストールしてから再インストールする方法しかありません。

> [!NOTE]
> 以下のいずれかの手順を実行して、問題の基になる原因を特定できない場合は、[プロセスモニター](https://docs.microsoft.com/sysinternals/downloads/procmon)セッションを試すことができます。 プロセスモニターは、レジストリとファイルシステムへのアクセスを記録する Sysinternals ツールです。

## <a name="related-topics"></a>関連項目

- [Teams のクライアントを取得する](get-clients.md)
- [Teams クライアントの更新プログラム](teams-client-update.md)