---
title: バージョンのサポート
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: この記事では、Microsoft Teams のルームのライフサイクルのサポートについて説明します。
ms.openlocfilehash: 55fde6317fe53102b97f752667d540e33a7b8c8c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675795"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams 室アプリバージョンのサポート
 
Microsoft Teams の会議室アプリは、1年に数回更新されます。 各更新プログラムは、GA (GA) のリリース日から12ヶ月の場合にサポートされています。 テクニカルサポートは12ヶ月全体に対応しています。 ただし、サポート構造は動的で、最新バージョンの可用性に依存する2つの個別のフェーズがあります。

- **サービスと重要な更新のフェーズ** \-最新バージョンの Microsoft Teams の会議アプリを実行すると、*セキュリティとサービス*の更新プログラムを含む定期的な更新プログラムを受け取ることになります。

- **セキュリティ更新プログラムのみのフェーズ** \- Microsoft Teams のルームアプリのリリースの新しいバージョンでは、古いバージョンのアプリでは、他の12ヶ月のライフサイクルに限定した*セキュリティ更新プログラムのみ*で、サポートレベルが低減されています。

> [!NOTE]
> 最新バージョンは、常にサービスと重要な更新プログラムの段階にあります。 重要な更新プログラムを提供するコードの問題が発生した場合は、最新バージョンもインストールされている必要があります。 サポートされているその他のすべてのバージョンは、セキュリティ更新プログラムを受け取ることができます。

すべてのサポートは、12ヶ月のバージョンのライフサイクルの有効期限が切れた後、または2つ以上の更新プログラムがリリースされてから終了します。 次に、お客様はサポートされているバージョンにアップデートする必要があります。

すべてのリリースは、 [Microsoft Teams ルームのリリースノート](srs2-release-note.md)に記載されています。

## <a name="windows-10-release-support"></a>Windows 10 リリースサポート

Microsoft Teams ルームを利用するには、半期チャネルサービスオプションで Windows 10 IoT Enterprise または Windows 10 Enterprise Sku が必要です。 以下の Windows 10 エディションはサポートされていません。

- Windows 10 Enterprise の長期サービスブランチ (LTSB)/長期サービスチャネル (LTSC) エディション
- Windows 10 インターネット (IoT) Enterprise LTSB/LTSC エディション
- windows 10 Pro または Home edition など、他のバージョンの Windows

Microsoft Teams の会議室デバイスでは、Windows 10 機能更新プログラムは、すぐには提供または更新されません。 [Windows 10 のリリース情報](https://docs.microsoft.com/windows/release-information/)ページで公開されている ga 日の間の、最大で6か月の遅延。 遅延時間は、Microsoft Teams 室のアプリケーション、デバイスハードウェア、および認定されたオーディオビデオ周辺機器について、Windows 10 のリリースとの互換性を検証するために使用されます。 検証が開始され、Windows 10 のメジャーリリースのアクティブな開発中に続行されます。 すべてのデバイスの製造元によってデバイスの更新された画像が構築されていることを確認する必要があります。また、Microsoft Teams がこれらの画像を認定およびテストします。 評価期間中、Microsoft Teams Room アプリは、windows 10 の機能更新プログラムを延期するために、[ビジネスグループポリシーの Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)を使用します。 互換性の問題が見つかり、解決した後、Windows ストアの新しいアプリのリリースでグループポリシーを更新することで、ブロックが解除されます。 Microsoft Teams の会議室アプリを実行するデバイスは、夜間メンテナンスの再起動中に、適切な Windows 10 リリースに自動的に更新されます。 MSI バージョンは、更新プログラムを手動で管理する必要があるユーザーに対して利用可能になります。  

> [!IMPORTANT]
> この検証期間中、Microsoft Teams 室のデバイスは、次の手段により、Windows 10 の次のリリースに更新さ**れない**ようにしてください。 これには、その場でのグループポリシーの上書き、または System Center やその他のサードパーティ製のデバイス管理サービスの使用が含まれます。 いずれの場合も、Microsoft Teams Room アプリケーションで問題が発生したり、デバイスが使用できなくなることがあります。  

次の表は、Microsoft Teams のルームをサポートしていることが確認された Windows 10 の推奨されるバージョンとサポートされるバージョンを示しています。 すべての日付は、ISO 8601 形式 (YYYY-MM-DD) で一覧表示されます。

|バージョン  |利用可能日   |Microsoft Teams ルームのサポート状態   |Microsoft Teams の会議室最小アプリケーションバージョン | OS ビルドの推奨  |
|:---  |:---       |:---                                  |:---     |:---     |
| 1903 |2019-05-21 |サポートされている &#x2780;、 <br/>推奨  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |まし <br/>推奨されない &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |サポート対象                             |4.1.22.0 |17134.191|
| 1709 |2018-01-18 |非サポート                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |サポート対象外                         |&#x2014; |&#x2014; |
||||||

Windows 10 1903 は、Intel グラフィックスデバイスドライバーの問題のため、Flex デバイスで Crestron は使用できません &#x2780;。 Windows 10 1903 はこれらのデバイスには提供されません。 ユーザーは、これらのデバイスを1903にアップグレードせず、グラフィックドライバーの更新が Crestron で利用できるようになるまで、それらのデバイスを Windows 10 1803 に残しておく必要があります。 

Microsoft Teams のルームアプリケーションでは互換性の問題が検出されたため、Windows 10 1809 のバージョン &#x2781; をお勧めしません。 この特定の問題により、Microsoft Teams のルームアプリケーションは、夜間の再起動後に起動できなくなります。 この問題は、Windows 10 1903 バージョンで解決されました。  

サポートされているバージョンの Windows 10 を使用する場合は、常に、Microsoft Teams の会議アプリの最新のアプリケーション更新プログラムが取得されます。  

## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams のルームリリースノート](srs2-release-note.md)

[Microsoft Teams のルームを計画する](skype-room-systems-v2-0.md)
