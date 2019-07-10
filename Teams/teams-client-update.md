---
title: チームの更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Teams デスクトップクライアントの更新方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35602272"
---
# <a name="teams-update-process"></a>Teams の更新プロセス

Teams web app が毎週更新されます。

Teams のデスクトップクライアントの更新プログラムは、skype の技術導入プログラムを通じて、社内の厳密なテストと検証の2週間ごとにリリースされます (タップ)。 通常、これは火曜日で行われます。 重要な更新が必要な場合は、チームはこのスケジュールを無視し、利用可能になったらすぐに更新プログラムをリリースします。

デスクトップクライアントは自動的に更新されます。 チームは、バックグラウンドで数時間ごとに更新プログラムを確認し、それをダウンロードした後、更新プログラムをサイレントインストールする前にコンピューターがアイドル状態になるまで待機します。

ユーザーは、アプリの右上にある [**プロファイル**] ドロップダウンメニューの [**更新プログラムの確認**] をクリックして、手動で更新プログラムをダウンロードすることもできます。 更新プログラムが利用可能な場合は、コンピューターがアイドル状態になったときにダウンロードされ、黙ってインストールされます。

更新プログラムをダウンロードするには、ユーザーがサインインしている必要があります。 

2019年7月9日に、Teams クライアントの更新では、更新中にネットワーク帯域幅が大幅に減少します。 これは既定でオンになっており、管理者またはユーザーが操作する必要はありません。


## <a name="what-about-updates-to-office-365-proplus"></a>Office 365 ProPlus の更新プログラムについて

Office は既定で、office 365 ProPlus の新しいインストールと共にインストールされます。詳しくは、「 [office 365 で Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/DeployOffice/teams-install)」を参照してください。 

チームは、前に説明したように、独自の更新プロセスに従いますが、Word や Excel など、他のオフィスアプリの更新プロセスではありません。 詳細については、「 [Office 365 ProPlus の更新プログラムチャネルの概要」](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)を参照してください。

## <a name="what-about-updates-to-teams-on-vdi"></a>VDI でのチームの更新について

仮想デスクトップインフラストラクチャ (VDI) 上の Teams クライアントは、非 VDI Teams クライアントのように自動的には更新されません。 「Team を[VDI にインストール](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)する」の手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。 最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>管理者がチームの自動更新の代わりに更新プログラムを展開することはできますか?

チームは、任意の配信メカニズムを使用して更新プログラムを展開する権限を管理者に付与することはできません。
