---
title: Teams の電話を Teams のディスプレイにアップグレードする
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Microsoft Teams 管理センターで Teams の電話を Teams の表示にアップグレードする方法について説明します。
ms.openlocfilehash: e741374ceb377dfec2f7b8a78f0d67b8e5a70bd1
ms.sourcegitcommit: 532205e5a3c28b44b86cd4d1376ebee9590b8266
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816117"
---
# <a name="upgrade-teams-phones-to-teams-displays"></a>Teams の電話を Teams のディスプレイにアップグレードする

> [!IMPORTANT]
> Teams ディスプレイへのアップグレードは、Lenovo ThinkSmart View デバイスでのみ利用可能です。 この記事の情報は、このデバイスモデルにのみ適用されます。  

この記事では、Microsoft Teams 管理センターでチームの電話を Teams 表示デバイスにアップグレードする方法の概要について説明します。 これにより、デバイスは、チームが表示するデバイスをユーザーに充実させることができます。

Teams の表示は、環境のタッチスクリーンを備えたオールインワンの専用チームデバイスのカテゴリであり、Cortana を搭載したハンズフリーの操作性を備えています。 Teams では、チームの電話の進化が表示されています。 Teams の [電話でサポートされている機能](phones-for-teams.md#features-supported-by-teams-phones)に加えて、teams には、すべてのチームアクティビティとコラボレーションオプションが常に使用できる、常に表示される機能などの機能も含まれています。 Teams の表示に固有の機能の詳細については、「 [Microsoft teams の表示](teams-displays.md)」を参照してください。

## <a name="what-you-need-to-know-about-upgrading-to-teams-displays"></a>Teams のディスプレイへのアップグレードについて知っておくべきこと

### <a name="which-teams-phones-can-be-upgraded"></a>どのチーム電話をアップグレードできますか?

Lenovo ThinkSmart View デバイスを Teams ディスプレイにアップグレードできます。

### <a name="how-can-i-prepare-users"></a>ユーザーを準備する方法を教えてください。

ユーザーを準備するには、チームの表示を使用して理解しやすくするために、ユーザーが [ [チーム表示](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6) ] を使って作業を開始してみましょう。 アップグレードを事前に行うことをお勧めします。

アップグレードした後で、データまたは設定が変更されていないことをユーザーに知らせます。 たとえば、チームの表示では、ユーザーは全員の会議、不在着信、ボイスメールにアクセスできます。 

### <a name="what-happens-after-the-upgrade"></a>アップグレード後はどうなりますか?

Teams の電話を Teams の表示デバイスにアップグレードすると、そのデバイスは、Microsoft Teams 管理センターの [ **デバイス** ] セクションに表示される [ **Teams の表示** ] ページに表示されます。 他の Teams デバイスを管理するのと同じ方法で管理します。 詳細については、「 [Teams でデバイスを管理](device-management.md)する」を参照してください。

Teams の電話を Teams の表示デバイスにアップグレードした後、操作を取り消すことはできないことに注意してください。 組織全体をアップグレードする前に、事前採用のグループと共にパイロットを実行することをお勧めします。 

## <a name="upgrade-your-teams-phones-to-teams-displays"></a>チームの電話を Teams の表示にアップグレードする

1. Microsoft Teams 管理センターの左のナビゲーションで、[ **デバイス**  >  **電話** ] に移動します。
2. アップグレードするチームの電話を選択し、[ **アップグレード** ] を選択します。

    :::image type="content" source="../media/upgrade-phones-to-displays-select.png" alt-text="[Teams にアップグレードするために選択したチームの電話番号を表示します。":::

3. [ **Teams へのアップグレード** ] ダイアログボックスで、[ **アップグレードのスケジュール** ] を選択して、アップグレードまたは **今すぐアップグレード** の日付と時刻を設定します。

    :::image type="content" source="../media/upgrade-phones-to-displays-upgrade.png" alt-text="[チームにアップグレード] ダイアログボックスが表示されたスクリーンショット":::

> [!NOTE]
> 選択した電話がアップグレードできないことを示すメッセージが表示された場合は、 [アップグレードをサポート](#which-teams-phones-can-be-upgraded)している電話が選択されていることを確認して、もう一度やり直してください。

アップグレードプロセス中、デバイスのファームウェアは、Teams の表示デバイスに更新され、デバイスは再起動され、使用できる状態になります。 アップグレードが完了すると、Microsoft Teams 管理センターに、[ **Teams の表示** ] ページに一覧表示されたデバイスが表示されます。

アップグレードが完了するまでに最長で1時間かかることがあります。 1時間経過しても処理が完了しない場合は、アップグレードを再試行してください。 [デバイスの詳細] ページの [ **履歴** ] タブに移動して、状態を確認することもできます。

## <a name="known-issues"></a>既知の問題

### <a name="teams-displays-have-the-default-theme-instead-of-the-dark-theme"></a>濃色テーマではなく、Teams の表示に既定のテーマが設定されている

Teams の表示での濃色テーマのサポートは、今後の更新プログラムで利用できるようになります。 濃色テーマを使用するチーム電話には、Teams へのアップグレード後に既定のテーマが表示されます。

### <a name="some-apps-are-missing-from-the-home-screen"></a>一部のアプリがホーム画面に表示されない

アップグレード後にホーム画面に特定のアプリが表示されない場合は、サインアウトして、もう一度サインインします。 この修正プログラムは今後の更新プログラムで提供される予定です。

## <a name="see-also"></a>関連項目

[Microsoft Teams の表示の概要](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams の表示](teams-displays.md)

[Teams Marketplace](https://office.com/teamsdevices)

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[Teams の Cortana 音声アシスタンス](https://docs.microsoft.com/MicrosoftTeams/cortana-in-teams)
