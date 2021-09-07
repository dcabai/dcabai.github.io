---
layout: single
title:  "Desinstalar el Cliente de Symantec Endpoint Protection (SEP)"
categories: symantec
tags: symantec legacy
date:   2009-07-19 05:50:23 -0400
classes: wide
---
Esta es una tarea sencilla siempre y cuando sale bien. Muchas veces la desinstalación sale bien según el asistente pero luego cuando lo reinstalamos podemos tener algún problema que arrastraba la versión anterior. Esto se debe a que al **remover el cliente de SEP** hay muchas entradas en el registro que no elimina. Esta basura que deja el SEP en nuestro registro de Windows debe ser eliminada a mano si queremos quitar todo rastro del producto de nuestros equipos.  
  
Acá dejo una lista de las entradas en el registro a eliminar y está en formato de batch, así que es tan sencillo como copiar y pegar el contenido que dejo a continuación en un notepad, guardarlo como **.cmd** o **.bat** y luego ejecutarlo en el equipo que ya hayan removido el cliente desde “Add & Remove Programs” o “Programs and Features”.  
  
Repito, esto es si el **cliente no funciona bien** contra la consola, y deben desinstalarlo y luego reinstalarlo y ven que el problema persiste. Si hacen la desinstalación del producto y luego al reinstalarlo queda todo bien entonces no hizo falta utilizar esto. Pero hay casos donde si deja esta basura en nuestro registro y tenemos que eliminarla a mano. Para esos casos si pueden utilizar las líneas que dejo a continuación.

```batch
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\*\\shellex\\ContextMenuHandlers\\LDVPMenu /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\ccEvtCli.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\ccProSub.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\ccSetEvt.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\ccSvcHst.exe /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\CliProxy.DLL] /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\HPPProtectionProviderUI.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\PatchWrap.EXE /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\ProtectionUtil.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\RTVScan.EXE /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SavMainUI.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SavUI.EXE /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SepLuCallback.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SescLU.EXE /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SmcGui.EXE /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SPBBCEVT.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\Srtsp32.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\AppID\\SyKnAppS.DLL /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\CcErrDsp.ErrorDisplay /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\CcErrDsp.ErrorDisplay.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\CcWebWnd.ccWebWindow /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\CcWebWnd.ccWebWindow.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\cliproxy.objects /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\cliproxy.objects.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Cliproxy.ScanManagerCOMCallback /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Cliproxy.ScanManagerCOMCallback.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Drive\\shellex\\ContextMenuHandlers\\LDVPMenu /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\EXCHNGUI.ExchngUICtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Folder\\shellex\\ContextMenuHandlers\\LDVPMenu /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.CAutoprotectFw /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.CAutoprotectFw.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.CCmcManagement /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.CCmcManagement.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.CNacManagement /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.CNacManagement.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.FwsProtectionProvider /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\FwsCtrl.FwsProtectionProvider.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\HPPProtectionProviderUI.HPPProtection /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\HPPProtectionProviderUI.HPPProtection.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\HPPProtectionProviderUI.HPPProtectionPr /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\HPPProtectionProviderUI.HPPProtectionProvider.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\INETMAILUI.InetMailUICtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Installer\\Features\\03E4A8BF51994184DA9F240ED0F9CDD3 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Installer\\Products\\03E4A8BF51994184DA9F240ED0F9CDD3 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Installer\\UpgradeCodes\\20A7FB42A06BB49448A397B3CB77ED4D /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDDATETIME.LDDateCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDDATETIME.LDStaticDateTimeCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDDATETIME.LDTimeCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPCTLS.LDVPActionsCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPCTLS.LDVPEditCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPCTLS.LDVPExtensionsCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPCTLS.LDVPResultsCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPCTLS.LDVPVirusDetailsCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPAboutDlgCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPCompressedCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPEmailNotifySettingsCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPMessageConfigCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPSchedule2Ctrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPScheduleCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPStorageViewCtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPDLGS.LDVPThreatExclusionsDlgCtl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LDVPUI.LDVPUICtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\LOTNOTESUI.LotNotesUICtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\PatchWrap.PatchWrapper /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\PatchWrap.PatchWrapper.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.ProtectionCollection /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.ProtectionCollection.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.ProtectionProviderColl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.ProtectionProviderCollec /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.Protection_GUID_Contai.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.Protection_GUID_Containe /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusFinder /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusFinder.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Autoprot.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Autoprotec /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Containe.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Container /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Definiti.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Definition /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_HostInte.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_HostIntegr /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_NetworkA.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_NetworkAcc /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_NetworkQ.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_NetworkQua /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_Provider.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_ProviderAu /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_ProviderEr /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\ProtectionUtil.StatusProblem_ProviderOf /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.CSavInfo /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.CSavInfo.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.CSavQuarantine /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.CSavQuarantine.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.OEMSettingsManager /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.OEMSettingsManager.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.ResultsViewCOMCallback /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.ResultsViewCOMCallback.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.ScanManagerService /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.ScanManagerService.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.VirusFoundCOMCallback /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Rtvscan.VirusFoundCOMCallback.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.ConfigureableScanCollection /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.ConfigureableScanCollection.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectExchange /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectExchange.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectFilesystem /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectFilesystem.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectInternetEmail /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectInternetEmail.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectNotes /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavAutoprotectNotes.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavConfigureableScan /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavConfigureableScan.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavProtectionProvider /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavProtectionProvider.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavQuarantineItem /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavQuarantineItem.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavQuarantineItemCollection /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.SavQuarantineItemCollection.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.TamperProtectionProvider /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.TamperProtectionProvider.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.TamperProtectProcess /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavMainUI.TamperProtectProcess.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavUI.ResultsViewCOMAdapter /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavUI.ResultsViewCOMAdapter.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavUI.VirusFoundCOMAdapter /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SavUI.VirusFoundCOMAdapter.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SEP.AV.ScanDlgs /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SepLuCallback.SepLuCallbackHandler /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SepLuCallback.SepLuCallbackHandler.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.AvLuCallback /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.AvLuCallback.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.ContentUpdateManager /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.ContentUpdateManager.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.MonikerInfo /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.MonikerInfo.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.MonikerInfoCollection /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.MonikerInfoCollection.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.SepContentService /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SescLu.SepContentService.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Shelsel2.Shelsel2 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Shelsel2.Shelsel2.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.ControlEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.ControlEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.ErrorEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.ErrorEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.MountEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.MountEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.NonViralEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.NonViralEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.StateChangeEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.StateChangeEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.ViralEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\srtsp32.ViralEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SyKnAppS.LUCallback /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SyKnAppS.LUCallback.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccEvtMgr.EventManager /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccEvtMgr.EventManager.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccEvtMgr.LogManager /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccEvtMgr.LogManager.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccEvtMgr.ModuleManager /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccEvtMgr.ModuleManager.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccProSub.ProviderProxy /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccProSub.ProviderProxy.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccProSub.SubscriberProxy /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccProSub.SubscriberProxy.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccSetEvt.SettingsChangeEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccSetEvt.SettingsChangeEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccSetMgr.SettingsService /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.CommonClient.ccSetMgr.SettingsService.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.SSHelper /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.SSHelper.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stCallbackManager /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stCallbackManager.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stCheckForUpdates /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stCheckForUpdates.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stDisScriptEngine /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stDisScriptEngine.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stHost /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stHost.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stHostCatalog /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stHostCatalog.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetBatchGet /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetBatchGet.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetConnParms /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetConnParms.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetGetFile /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetGetFile.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetTransferItem /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stInetTransferItem.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stLog /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stLog.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stLUProgressCallback /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stLUProgressCallback.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stPatch /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stPatch.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stPatchCatalog /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stPatchCatalog.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stSettings /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.stSettings.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.SymNeti.SymNetiProviderProxy /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.SymNeti.SymNetiProviderProxy.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.SymNeti.SymNetiSubscriberProxy /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\Symantec.SymNeti.SymNetiSubscriberProxy.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.AlertEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.AlertEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.LocationChangeEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.LocationChangeEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.LocationEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.LocationEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.LogEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.LogEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.NetworkChangeEvent /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SymNeti.NetworkChangeEvent.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\SYMPROTECTUI.SymProtectUICtrl.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\TSSAFILE /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\VpshellEx.VpshellEx /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Classes\\VpshellEx.VpshellEx.1 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Intel\\LANDesk\\AMS2 /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\ESENT\\Process\\ccSvcHst /va /f 
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Exchange\\Client\\Extensions /v Outlook Setup Extension /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Exchange\\Client\\Extensions /v Symantec AntiVirus Outlook Protection /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\RFC1156Agent /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\App Paths\\ccApp.exe /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\App Paths\\Smc.exe /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Controls Folder\\Display\\shellex\\PropertySheetHandlers\\LDVP Shell Extensions /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UpgradeCodes\\20A7FB42A06BB49448A397B3CB77ED4D /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Installer\\UserData\\S-1-5-18\\Products\\03E4A8BF51994184DA9F240ED0F9CDD3 /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Run /v ccApp /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ShellExtensions\\Approved /v {8BEEE74D-455E-4616-A97A-F6E86C317F32} /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\COH_PVLInfo /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\Common Client /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v AMSUsageCount /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v COHDataDIR /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v COHDIR /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v GEH /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v IPSEngine /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v MSL /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SAV Install Directory /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SAVCE /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v Savrt /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SavSubmissionEngine /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SavSubmissionEngineData /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SPBBC /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SRTSP /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SRTSPQuarantine /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SyKnAppS /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SYKNAPPSDEF /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v SymNetDrv /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v VP6ClientInstalled /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\InstalledApps /v VP6UsageCount /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\PatchInst /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\SPBBC /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\SRTSP /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\SyKnAppS /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\Symantec AntiVirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\Symantec Endpoint Protection /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\SymNetDrv /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SOFTWARE\\Symantec\\VxMSLight /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Minimal\\ccEvtMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Minimal\\ccSetMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Minimal\\Symantec Antivirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Minimal\\Symantec Antvirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Network\\ccEvtMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Network\\ccSetMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Network\\SmcService /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Network\\Symantec Antivirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\SafeBoot\\Network\\Symantec Antvirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ccEvtMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\ccSetMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\COH_Mon /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Eventlog\\Application\\ccEvtMgr /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Eventlog\\Application\\ccSvcHst /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Eventlog\\Application\\Symantec AntiVirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Eventlog\\System\\SRTSP /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Eventlog\\System\\SRTSPL /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v ConfigUiPath /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v IdentityPath /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v InteractiveUIPath /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v Path /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v ConfigUiPathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v IdentityPathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v InteractiveUIPathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\13 /v PathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v ConfigUiPath /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v IdentityPath /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v InteractiveUIPath /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v Path /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v ConfigUiPathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v IdentityPathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v InteractiveUIPathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\25 /v PathBackup /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP\\88 /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SmcService /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SNAC /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SnacNp /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SPBBCDrv /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SRTSP /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SRTSPL /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SRTSPX /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Symantec AntiVirus /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SYMREDRV /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SYMTDI /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\SysPlant /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\vsdatant /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\WPS /va /f
REG DELETE HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\WpsHelper /va /f
SHUTDOWN -r -t 01
```
Una vez que tengan el batch armado pueden ejecutarlo luego de haber desinstalado el cliente y luego de haber reiniciado. Este batch luego de eliminar las entradas en el registro también reinicia el equipo automáticamente. Al finalizar esto se puede instalar el cliente de nuevo y que tenga todas las configuraciones de cero. Espero les sirva.