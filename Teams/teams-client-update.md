---
title: チーム プロセスを更新します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: チームのデスクトップ クライアントを更新する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829097"
---
# <a name="teams-update-process"></a>チーム プロセスを更新します。

チームの Web アプリケーションは、毎週更新されます。

チーム デスクトップ クライアント更新がリリースされた内部の厳格なテストおよび検証した後は 2 週間ごと、技術導入プログラム (タップ) を使用します。 これは通常、火曜日にします。 重要な更新が必要な場合は、チームはこのスケジュールを使用しないし、使用可能になるとすぐに更新プログラムをリリースします。

デスクトップ クライアント自体が自動的に更新します。 チームのチェックは、バック グラウンドでいくつかの時間ごとの更新、ダウンロード、および、コンピューターに更新プログラムをサイレント モードでインストールする前にアイドル状態になるを待ちます。

上に**プロファイル**のドロップ ダウン メニューで [**更新プログラムの確認**] をクリックしてユーザーが更新プログラムを手動でダウンロード、アプリケーションの右です。 更新が利用可能な場合は、それがダウンロードされ、コンピューターがアイドル状態のときにサイレント モードでインストールされています。

ユーザーは、ダウンロードする更新プログラム署名する必要があります。

## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 用リソースへの更新について教えてください。

チームは Office 365 用リソースの新規インストールでは既定でインストールされている[Office 365 用リソースを持つマイクロソフト チームの展開](https://docs.microsoft.com/DeployOffice/teams-install)で説明したようです。 

チームは、上記で説明した、独自の更新プロセスと、更新プロセスではなく Word や Excel など、他のオフィス アプリケーションに依存します。

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI のチームへの更新について教えてください。

チーム クライアント仮想デスクトップ インフラストラクチャ (VDI) では、VDI 以外のチームのクライアントがいることを自動的に更新されません。 [VDI のチームをインストール](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)する手順の説明に従って、新しい MSI をインストールすると、VM イメージを更新する必要があります。 新しいバージョンに更新する現在のバージョンをアンインストールする必要があります。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理者は、チームではなく更新プログラムを展開できる自動更新しますか?

チームは、管理者が任意のデリバリ メカニズムを通じて更新プログラムを展開することを得られないは。
