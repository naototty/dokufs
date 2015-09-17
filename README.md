# dokufs
A fuse filesystem for DokuWiki implemented in Ruby.

DokuFS is a filesystem that allows, with the help of Fuse, to mount a DokuWiki over XML-RPC into you local filesystem on Linux

  * fuse : http://en.wikipedia.org/wiki/Filesystem_in_Userspace
  * DokuWiki : http://www.dokuwiki.org/wiki%3ADokuWiki
  * xml-rpc : http://en.wikipedia.org/wiki/XML-RPC

You are then able to browse the filesystem and to create, edit or delete files, that means to create, edit or delete pages or media files on the Wiki you have mounted. Deleting, moving and copying of whole namespaces should work, too (however the history of pages is not moved).

All pages have the extension .dw so you can easily handle syntax highlighting (syntax highlighting for vim is included in the unfortunately discontinued DokuVimKi project, though you don't need the rest of DokuVimKi when using DokuFS).

  * DokuVimKi : https://github.com/chimeric/dokuwikixmlrpc

DokuFS supports two modes – one for pages and one for media files. In the mode for pages the creation of other files but those with the extension .dw isn't allowed (temporary files of VIM and Emacs are handled in memory). In the mode for media files every file is simply uploaded to the DokuWiki, so basically all file types are allowed that are supported by your DokuWiki installation.

Every 5 minutes, the recent changes of the Wiki are pulled and the directory structure is updated. Once a page is downloaded it will be in a cache (with a memory limit) so that only the first read/size-request will be slow.



## project site
https://www.content-space.de/dokuwiki/projekte/dokufs

