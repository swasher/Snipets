    import timeit
    if __name__ == '__main__':
        print(timeit.timeit("my_function()", number=1000, globals=locals()))
