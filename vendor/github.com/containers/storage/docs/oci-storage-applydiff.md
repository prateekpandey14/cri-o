## oci-storage-apply-diff 1 "August 2016"

## NAME
oci-storage apply-diff - Apply a layer diff to a layer

## SYNOPSIS
**oci-storage** **apply-diff** [*options* [...]] *layerNameOrID* [*referenceLayerNameOrID*]

## DESCRIPTION
When a layer is first created, it contains no changes relative to its parent
layer.  The layer can either be mounted read-write and its contents modified
directly, or contents can be added (or removed) by applying a layer diff.  A
layer diff takes the form of a (possibly compressed) tar archive with
additional information present in its headers, and can be produced by running
*oci-storage diff* or an equivalent.

Layer diffs are not typically applied manually.  More often they are applied by
a tool which is being used to import an entire image, such as **skopeo**.

## OPTIONS
**-f | --file** *filename*

Specifies the name of a file from which the diff should be read.  If this
option is not used, the diff is read from standard input.

## EXAMPLE
**oci-storage apply-diff -f 71841c97e320d6cde.tar.gz layer1**

## SEE ALSO
oci-storage-changes(1)
oci-storage-diff(1)
oci-storage-diffsize(1)
